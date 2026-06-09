# FLTI_AddNew(AutoPtr<FileLogThreadInfo> *)

- ea: `0x180038c50`
- end: `0x180038df6`
- name: `?FLTI_AddNew@@YAJPEAV?$AutoPtr@UFileLogThreadInfo@@@@@Z`
- size: `422`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18004eb38`

## callees

- `0x180016454`
- `0x180029b70`
- `0x180037424`
- `0x180037458`
- `0x180038c50`
- `0x18003d294`
- `0x18004dff0`
- `0x18004e520`
- `0x18004e57c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180038d35`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180038d9a`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180038d35`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180038d9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038cb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038cb4`
- `ntdll!RtlConvertSharedToExclusive` at `0x180038d22`
- `ntdll!RtlConvertSharedToExclusive` at `0x180038d22`
- `ntdll!RtlConvertExclusiveToShared` at `0x180038dd3`
- `ntdll!RtlConvertExclusiveToShared` at `0x180038dd3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FLTI_AddNew(void **a1)
{
  volatile signed __int32 *v1; // rbx
  _BYTE *v2; // rcx
  int v3; // ebx
  __int64 *v4; // rcx
  volatile signed __int32 **v5; // rdx
  volatile signed __int32 *v6; // rax
  unsigned int v8; // eax
  _BYTE v9[24]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v10[24]; // [rsp+38h] [rbp-30h] BYREF
  int v11; // [rsp+50h] [rbp-18h]
  volatile signed __int32 *v13; // [rsp+78h] [rbp+10h] BYREF
  volatile signed __int32 *v14; // [rsp+80h] [rbp+18h] BYREF
  __int64 v15; // [rsp+88h] [rbp+20h]

  v1 = (volatile signed __int32 *)operator new(0x30u);
  v13 = v1;
  AutoPtr<FileLogThreadInfo>::AutoPtr<FileLogThreadInfo>((_QWORD *)v1 + 2, 0);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>((_QWORD *)v1 + 3);
  AutoPtr<FileLogThreadInfo>::AutoPtr<FileLogThreadInfo>(&v14, (__int64)v1);
  if ( v14 && (v2 = (_BYTE *)*((_QWORD *)v14 + 1)) != 0 )
  {
    *v2 = 1;
    *(_DWORD *)(*((_QWORD *)v14 + 1) + 8LL) = GetCurrentThreadId();
    *(_DWORD *)(*((_QWORD *)v14 + 1) + 4LL) = 256;
    AutoPtr<FileLogThreadInfo>::AutoPtr<FileLogThreadInfo>(&v13, 0);
    AutoPtr<FileLogBuffer>::operator=(*((_QWORD *)v14 + 1) + 16LL, &v13);
    AutoPtr<FileLogBuffer>::~AutoPtr<FileLogBuffer>(&v13);
    RtlConvertSharedToExclusive((PRTL_RESOURCE)((char *)_pflstate + 216));
    v15 = _set_se_translator(SeTransFunc);
    v3 = 0;
    try
    {
      v4 = (__int64 *)*((_QWORD *)_pflstate + 9);
      v5 = (volatile signed __int32 **)v4[1];
      if ( v5 == (volatile signed __int32 **)v4[2] )
      {
        std::vector<AutoPtr<FileLogThreadInfo>,MyThrowingAllocator<AutoPtr<FileLogThreadInfo>>>::_Emplace_reallocate<AutoPtr<FileLogThreadInfo> const &>(
          v4,
          v5,
          &v14);
      }
      else
      {
        v6 = v14;
        *v5 = v14;
        if ( v6 )
          _InterlockedIncrement(v6);
        v4[1] += 8;
      }
    }
    catch ( SeException v10 )
    {
      v8 = v11;
      if ( v11 > 0 )
        v8 = (unsigned __int16)v11 | 0x80070000;
      LODWORD(v13) = v8;
      SeException::~SeException((SeException *)v10);
      v3 = (int)v13;
    }
    catch ( std::bad_alloc v9 )
    {
      LODWORD(v13) = -2147024882;
      SeException::~SeException((SeException *)v9);
      v3 = (int)v13;
    }
    catch ( ... )
    {
      LODWORD(v13) = -2147418113;
      v3 = (int)v13;
    }
    _set_se_translator(v15);
    if ( v3 >= 0 )
    {
      AutoPtr<FileLogThreadInfo>::operator=(a1, &v14);
      v3 = 0;
    }
  }
  else
  {
    v3 = -2147024882;
  }
  RtlConvertExclusiveToShared((PRTL_RESOURCE)((char *)_pflstate + 216));
  AutoPtr<FileLogThreadInfo>::~AutoPtr<FileLogThreadInfo>(&v14);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180038c50  mov     [rsp+arg_0], rcx
0x180038c55  push    rbx
0x180038c56  sub     rsp, 60h
0x180038c5a  mov     ecx, 30h ; '0'; Size
0x180038c5f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038c64  mov     rbx, rax
0x180038c67  mov     [rsp+68h+arg_8], rax
0x180038c6c  lea     rcx, [rax+10h]
0x180038c70  xor     edx, edx
0x180038c72  call    ??0?$AutoPtr@UFileLogThreadInfo@@@@QEAA@PEAUFileLogThreadInfo@@@Z; AutoPtr<FileLogThreadInfo>::AutoPtr<FileLogThreadInfo>(FileLogThreadInfo *)
0x180038c77  nop
0x180038c78  lea     rcx, [rbx+18h]
0x180038c7c  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180038c81  nop
0x180038c82  mov     rdx, rbx
0x180038c85  lea     rcx, [rsp+68h+arg_10]
0x180038c8d  call    ??0?$AutoPtr@UFileLogThreadInfo@@@@QEAA@PEAUFileLogThreadInfo@@@Z; AutoPtr<FileLogThreadInfo>::AutoPtr<FileLogThreadInfo>(FileLogThreadInfo *)
0x180038c92  nop
0x180038c93  mov     rax, [rsp+68h+arg_10]
0x180038c9b  test    rax, rax
0x180038c9e  jz      loc_180038DC0
0x180038ca4  mov     rcx, [rax+8]
0x180038ca8  test    rcx, rcx
0x180038cab  jz      loc_180038DC0
0x180038cb1  mov     byte ptr [rcx], 1
0x180038cb4  call    cs:__imp_GetCurrentThreadId
0x180038cbb  nop     dword ptr [rax+rax+00h]
0x180038cc0  mov     rcx, [rsp+68h+arg_10]
0x180038cc8  mov     rdx, [rcx+8]
0x180038ccc  mov     [rdx+8], eax
0x180038ccf  mov     rax, [rsp+68h+arg_10]
0x180038cd7  mov     rcx, [rax+8]
0x180038cdb  mov     dword ptr [rcx+4], 100h
0x180038ce2  xor     edx, edx
0x180038ce4  lea     rcx, [rsp+68h+arg_8]
0x180038ce9  call    ??0?$AutoPtr@UFileLogThreadInfo@@@@QEAA@PEAUFileLogThreadInfo@@@Z; AutoPtr<FileLogThreadInfo>::AutoPtr<FileLogThreadInfo>(FileLogThreadInfo *)
0x180038cee  nop
0x180038cef  mov     rax, [rsp+68h+arg_10]
0x180038cf7  mov     rcx, [rax+8]
0x180038cfb  add     rcx, 10h
0x180038cff  lea     rdx, [rsp+68h+arg_8]
0x180038d04  call    ??4?$AutoPtr@UFileLogBuffer@@@@QEAAAEAV0@AEBV0@@Z; AutoPtr<FileLogBuffer>::operator=(AutoPtr<FileLogBuffer> const &)
0x180038d09  nop
0x180038d0a  lea     rcx, [rsp+68h+arg_8]
0x180038d0f  call    ??1?$AutoPtr@UFileLogBuffer@@@@QEAA@XZ; AutoPtr<FileLogBuffer>::~AutoPtr<FileLogBuffer>(void)
0x180038d14  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180038d1b  add     rcx, 0D8h; Resource
0x180038d22  call    cs:__imp_RtlConvertSharedToExclusive
0x180038d29  nop     dword ptr [rax+rax+00h]
0x180038d2e  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x180038d35  call    cs:__imp__set_se_translator
0x180038d3c  nop     dword ptr [rax+rax+00h]
0x180038d41  mov     [rsp+68h+arg_18], rax
0x180038d49  xor     ebx, ebx
0x180038d4b  mov     rax, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180038d52  mov     rcx, [rax+48h]
0x180038d56  mov     rdx, [rcx+8]
0x180038d5a  cmp     rdx, [rcx+10h]
0x180038d5e  jz      short loc_180038D7A
0x180038d60  mov     rax, [rsp+68h+arg_10]
0x180038d68  mov     [rdx], rax
0x180038d6b  test    rax, rax
0x180038d6e  jz      short loc_180038D73
0x180038d70  lock inc dword ptr [rax]
0x180038d73  add     qword ptr [rcx+8], 8
0x180038d78  jmp     short loc_180038D88
0x180038d7a  lea     r8, [rsp+68h+arg_10]
0x180038d82  call    ??$_Emplace_reallocate@AEBV?$AutoPtr@UFileLogThreadInfo@@@@@?$vector@V?$AutoPtr@UFileLogThreadInfo@@@@V?$MyThrowingAllocator@V?$AutoPtr@UFileLogThreadInfo@@@@@@@std@@AEAAPEAV?$AutoPtr@UFileLogThreadInfo@@@@QEAV2@AEBV2@@Z; std::vector<AutoPtr<FileLogThreadInfo>,MyThrowingAllocator<AutoPtr<FileLogThreadInfo>>>::_Emplace_reallocate<AutoPtr<FileLogThreadInfo> const &>(AutoPtr<FileLogThreadInfo> * const,AutoPtr<FileLogThreadInfo> const &)
0x180038d87  nop
0x180038d88  jmp     short loc_180038D92
0x180038d8a  jmp     short loc_180038D8E
0x180038d8c  jmp     short $+2
0x180038d8e  mov     ebx, dword ptr [rsp+68h+arg_8]
0x180038d92  mov     rcx, [rsp+68h+arg_18]
0x180038d9a  call    cs:__imp__set_se_translator
0x180038da1  nop     dword ptr [rax+rax+00h]
0x180038da6  test    ebx, ebx
0x180038da8  js      short loc_180038DC5
0x180038daa  lea     rdx, [rsp+68h+arg_10]
0x180038db2  mov     rcx, [rsp+68h+arg_0]
0x180038db7  call    ??4?$AutoPtr@UFileLogThreadInfo@@@@QEAAAEAV0@AEBV0@@Z; AutoPtr<FileLogThreadInfo>::operator=(AutoPtr<FileLogThreadInfo> const &)
0x180038dbc  xor     ebx, ebx
0x180038dbe  jmp     short loc_180038DC5
0x180038dc0  mov     ebx, 8007000Eh
0x180038dc5  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180038dcc  add     rcx, 0D8h; Resource
0x180038dd3  call    cs:__imp_RtlConvertExclusiveToShared
0x180038dda  nop     dword ptr [rax+rax+00h]
0x180038ddf  nop
0x180038de0  lea     rcx, [rsp+68h+arg_10]
0x180038de8  call    ??1?$AutoPtr@UFileLogThreadInfo@@@@QEAA@XZ; AutoPtr<FileLogThreadInfo>::~AutoPtr<FileLogThreadInfo>(void)
0x180038ded  mov     eax, ebx
0x180038def  add     rsp, 60h
0x180038df3  pop     rbx
0x180038df4  retn
```
