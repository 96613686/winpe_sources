# ATL::CComObject<CWdsDeviceControllerRequest>::CreateInstance(ATL::CComObject<CWdsDeviceControllerRequest> * *)

- ea: `0x180001be0`
- end: `0x180001cca`
- name: `?CreateInstance@?$CComObject@VCWdsDeviceControllerRequest@@@ATL@@SAJPEAPEAV12@@Z`
- size: `234`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800014c4`
- `0x180003508`

## callees

- `0x180001be0`
- `0x180001cd0`
- `0x180015068`
- `0x180015c9d`
- `0x180015cc0`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180001c32`
- `KERNEL32!InitializeCriticalSection` at `0x180001c32`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsDeviceControllerRequest>::CreateInstance(_QWORD *a1)
{
  int v2; // esi
  _DWORD *v3; // rax
  _DWORD *v4; // rdi
  __int64 result; // rax

  *a1 = 0;
  v2 = -2147024882;
  v3 = operator new(0x8B8u);
  v4 = v3;
  if ( v3 )
  {
    v3[2] = 0;
    memset_0(v3 + 4, 0, 0x28u);
    *((_BYTE *)v4 + 56) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v4 + 16));
    *((_QWORD *)v4 + 13) = 0;
    v4[28] = 0;
    memset_0(v4 + 29, 0, 0x838u);
    *((_QWORD *)v4 + 278) = 0;
    *(_QWORD *)v4 = &ATL::CComObject<CWdsDeviceControllerRequest>::`vftable';
    _InterlockedIncrement((volatile signed __int32 *)ATL::_pAtlModule + 3);
  }
  else
  {
    v4 = 0;
  }
  if ( v4 )
  {
    v2 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v4 + 4));
    if ( v2 >= 0 )
    {
      *((_BYTE *)v4 + 56) = 1;
      v2 = 0;
    }
    if ( v2 )
    {
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v4 + 72LL))(v4, 1);
      v4 = 0;
    }
  }
  result = (unsigned int)v2;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180001be0  mov     rax, rsp
0x180001be3  mov     [rax+8], rbx
0x180001be7  mov     [rax+10h], rbp
0x180001beb  mov     [rax+18h], rsi
0x180001bef  mov     [rax+20h], rdi
0x180001bf3  push    r14
0x180001bf5  sub     rsp, 20h
0x180001bf9  mov     r14, rcx
0x180001bfc  xor     ebp, ebp
0x180001bfe  mov     [rcx], rbp
0x180001c01  mov     esi, 8007000Eh
0x180001c06  mov     ecx, 8B8h; Size
0x180001c0b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001c10  mov     rdi, rax
0x180001c13  test    rax, rax
0x180001c16  jz      short loc_180001C6E
0x180001c18  xor     edx, edx; Val
0x180001c1a  mov     [rax+8], ebp
0x180001c1d  lea     r8d, [rbp+28h]; Size
0x180001c21  lea     rcx, [rax+10h]; void *
0x180001c25  call    memset_0
0x180001c2a  lea     rcx, [rdi+40h]; lpCriticalSection
0x180001c2e  mov     [rdi+38h], bpl
0x180001c32  call    cs:__imp_InitializeCriticalSection
0x180001c38  lea     rcx, [rdi+74h]; void *
0x180001c3c  mov     [rdi+68h], rbp
0x180001c40  xor     edx, edx; Val
0x180001c42  mov     [rdi+70h], ebp
0x180001c45  mov     r8d, 838h; Size
0x180001c4b  call    memset_0
0x180001c50  lea     rax, ??_7?$CComObject@VCWdsDeviceControllerRequest@@@ATL@@6B@; const ATL::CComObject<CWdsDeviceControllerRequest>::`vftable'
0x180001c57  mov     [rdi+8B0h], rbp
0x180001c5e  mov     [rdi], rax
0x180001c61  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001c68  lock inc dword ptr [rax+0Ch]
0x180001c6c  jmp     short loc_180001C71
0x180001c6e  mov     rdi, rbp
0x180001c71  test    rdi, rdi
0x180001c74  jz      short loc_180001CAA
0x180001c76  lea     rcx, [rdi+10h]; this
0x180001c7a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001c7f  mov     esi, eax
0x180001c81  test    eax, eax
0x180001c83  js      short loc_180001C89
0x180001c85  mov     byte ptr [rdi+38h], 1
0x180001c89  test    esi, esi
0x180001c8b  cmovns  esi, ebp
0x180001c8e  test    esi, esi
0x180001c90  jz      short loc_180001CAA
0x180001c92  mov     r8, [rdi]
0x180001c95  mov     edx, 1
0x180001c9a  mov     rcx, rdi
0x180001c9d  mov     rax, [r8+48h]
0x180001ca1  call    cs:__guard_dispatch_icall_fptr
0x180001ca7  mov     rdi, rbp
0x180001caa  mov     rbx, [rsp+28h+arg_0]
0x180001caf  mov     eax, esi
0x180001cb1  mov     rsi, [rsp+28h+arg_10]
0x180001cb6  mov     rbp, [rsp+28h+arg_8]
0x180001cbb  mov     [r14], rdi
0x180001cbe  mov     rdi, [rsp+28h+arg_18]
0x180001cc3  add     rsp, 20h
0x180001cc7  pop     r14
0x180001cc9  retn
```
