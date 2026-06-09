# CWMPerStreamIndex::DumpSimpleIndexObjectToFile(void *,CASFMMStream *,ulong *)

- ea: `0x18000f390`
- end: `0x18000f5c6`
- name: `?DumpSimpleIndexObjectToFile@CWMPerStreamIndex@@UEAAJPEAXPEAVCASFMMStream@@PEAK@Z`
- size: `566`
- prototype: `__int64 __fastcall(CWMPerStreamIndex *__hidden this, void *, struct CASFMMStream *, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180001194`
- `0x1800011ec`
- `0x1800015f0`
- `0x18000f390`
- `0x180015e80`
- `0x18001e790`
- `0x180024a54`
- `0x180024be4`
- `0x18002b010`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18000f554`
- `KERNEL32!WriteFile` at `0x18000f554`

## pseudocode

```c
__int64 __fastcall CWMPerStreamIndex::DumpSimpleIndexObjectToFile(
        CWMPerStreamIndex *this,
        void *a2,
        struct CASFMMStream *a3,
        unsigned int *a4)
{
  unsigned int v4; // r15d
  __int64 v8; // rax
  char *v9; // rsi
  __int64 v10; // rax
  GUID v11; // xmm0
  unsigned int v12; // edx
  int v13; // ebx
  __int64 v14; // rax
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // rdx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-79h] BYREF
  HANDLE hFile; // [rsp+38h] [rbp-71h]
  unsigned int v20[4]; // [rsp+40h] [rbp-69h] BYREF
  char *v21; // [rsp+50h] [rbp-59h]
  int v22; // [rsp+58h] [rbp-51h]
  int v23; // [rsp+5Ch] [rbp-4Dh]
  _QWORD v24[2]; // [rsp+60h] [rbp-49h] BYREF
  GUID v25; // [rsp+70h] [rbp-39h]
  __int64 v26; // [rsp+88h] [rbp-21h]
  __int64 v27; // [rsp+90h] [rbp-19h]
  GUID v28; // [rsp+98h] [rbp-11h]
  __int64 v29; // [rsp+A8h] [rbp-1h]
  __int64 v30; // [rsp+B0h] [rbp+7h]
  __int64 v31; // [rsp+B8h] [rbp+Fh]

  v4 = 0;
  hFile = a2;
  if ( !a3 || a2 == (void *)-1LL )
    return 2147942487LL;
  v8 = *(_QWORD *)&CLSID_AsfXStreamTypeIcmVideo.Data1 - *(_QWORD *)((char *)this + 28);
  if ( *(_QWORD *)&CLSID_AsfXStreamTypeIcmVideo.Data1 == *(_QWORD *)((char *)this + 28) )
    v8 = *(_QWORD *)CLSID_AsfXStreamTypeIcmVideo.Data4 - *(_QWORD *)((char *)this + 36);
  if ( v8 )
  {
    if ( *a4 )
      *a4 = 0;
    return 0;
  }
  else
  {
    v26 = 0;
    v24[0] = &CASFIndexObject::`vftable';
    v9 = 0;
    v10 = *((_QWORD *)a3 + 77);
    v27 = 1;
    v24[1] = 108;
    v31 = 0;
    v30 = 0;
    v25 = CLSID_CAsfIndexObjectV2;
    if ( v10 )
      v11 = *(GUID *)(v10 + 72);
    else
      v11 = GUID_NULL;
    v12 = *((_DWORD *)this + 20);
    v29 = *((_QWORD *)this + 1);
    v28 = v11;
    v13 = CASFIndexObject::SetEntryCount((CASFIndexObject *)v24, v12);
    if ( v13 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 34) + 40LL))((char *)this + 272);
      if ( v13 >= 0 )
      {
        if ( *((_DWORD *)this + 20) )
        {
          while ( 1 )
          {
            v14 = *((_QWORD *)this + 34);
            *(_OWORD *)v20 = 0;
            v13 = (*(__int64 (__fastcall **)(char *, unsigned int *))(v14 + 48))((char *)this + 272, v20);
            if ( v13 < 0 )
              break;
            v13 = CASFIndexObject::SetIndexEntry((CASFIndexObject *)v24, v4, v20[0], v20[2]);
            if ( v13 < 0 )
              break;
            if ( ++v4 >= *((_DWORD *)this + 20) )
              goto LABEL_15;
          }
        }
        else
        {
LABEL_15:
          v15 = (unsigned int)(6 * v30 + 56);
          v9 = (char *)operator new[](v15);
          if ( v9 )
          {
            v23 = *((_DWORD *)a3 + 166);
            *(_QWORD *)v20 = v9;
            v21 = &v9[v15];
            *(_QWORD *)&v20[2] = v9;
            v22 = 1;
            NumberOfBytesWritten = 0;
            v13 = CASFIndexObject::Persist((CASFIndexObject *)v24, (struct CASFArchive *)v20);
            if ( WriteFile(hFile, v9, v15, &NumberOfBytesWritten, 0) && NumberOfBytesWritten >= (unsigned int)v15 )
            {
              if ( a4 )
                *a4 = NumberOfBytesWritten;
            }
            else
            {
              v13 = -2147467259;
            }
          }
          else
          {
            v13 = -2147024882;
          }
        }
      }
    }
    CASFIndexObject::~CASFIndexObject((CASFIndexObject *)v24);
    if ( v9 )
      operator delete(v9, v16);
    return (unsigned int)v13;
  }
}

```

## disassembly

```asm
0x18000f390  mov     [rsp-8+arg_10], rbx
0x18000f395  push    rbp
0x18000f396  push    rsi
0x18000f397  push    rdi
0x18000f398  push    r12
0x18000f39a  push    r13
0x18000f39c  push    r14
0x18000f39e  push    r15
0x18000f3a0  lea     rbp, [rsp-27h]
0x18000f3a5  sub     rsp, 0D0h
0x18000f3ac  mov     rax, cs:__security_cookie
0x18000f3b3  xor     rax, rsp
0x18000f3b6  mov     [rbp+57h+var_40], rax
0x18000f3ba  xor     r15d, r15d
0x18000f3bd  mov     [rbp+57h+hFile], rdx
0x18000f3c1  mov     r14, r9
0x18000f3c4  mov     r13, r8
0x18000f3c7  mov     rax, rdx
0x18000f3ca  mov     rdi, rcx
0x18000f3cd  test    r8, r8
0x18000f3d0  jz      loc_18000F59A
0x18000f3d6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f3da  jz      loc_18000F59A
0x18000f3e0  mov     rax, qword ptr cs:CLSID_AsfXStreamTypeIcmVideo.Data1
0x18000f3e7  sub     rax, [rcx+1Ch]
0x18000f3eb  jnz     short loc_18000F3F8
0x18000f3ed  mov     rax, qword ptr cs:CLSID_AsfXStreamTypeIcmVideo.Data4
0x18000f3f4  sub     rax, [rcx+24h]
0x18000f3f8  test    rax, rax
0x18000f3fb  jnz     loc_18000F58E
0x18000f401  movups  xmm0, xmmword ptr cs:CLSID_CAsfIndexObjectV2.Data1
0x18000f408  lea     rax, ??_7CASFIndexObject@@6B@; const CASFIndexObject::`vftable'
0x18000f40f  mov     [rbp+57h+var_78], r15
0x18000f413  mov     [rbp+57h+var_A0], rax
0x18000f417  mov     rsi, r15
0x18000f41a  mov     rax, [r8+268h]
0x18000f421  mov     [rbp+57h+var_70], 1
0x18000f429  mov     [rbp+57h+var_98], 6Ch ; 'l'
0x18000f431  mov     [rbp+57h+var_48], r15
0x18000f435  mov     [rbp+57h+var_50], r15
0x18000f439  movdqu  [rbp+57h+var_90], xmm0
0x18000f43e  test    rax, rax
0x18000f441  jz      short loc_18000F449
0x18000f443  movups  xmm0, xmmword ptr [rax+48h]
0x18000f447  jmp     short loc_18000F450
0x18000f449  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000f450  mov     rax, [rcx+8]
0x18000f454  mov     edx, [rcx+50h]; unsigned int
0x18000f457  lea     rcx, [rbp+57h+var_A0]; this
0x18000f45b  mov     [rbp+57h+var_58], rax
0x18000f45f  movdqu  [rbp+57h+var_68], xmm0
0x18000f464  call    ?SetEntryCount@CASFIndexObject@@QEAAJK@Z; CASFIndexObject::SetEntryCount(ulong)
0x18000f469  mov     ebx, eax
0x18000f46b  test    eax, eax
0x18000f46d  js      loc_18000F574
0x18000f473  lea     r12, [rdi+110h]
0x18000f47a  mov     rax, [r12]
0x18000f47e  mov     rcx, r12
0x18000f481  mov     rax, [rax+28h]
0x18000f485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f48a  mov     ebx, eax
0x18000f48c  test    eax, eax
0x18000f48e  js      loc_18000F574
0x18000f494  cmp     [rdi+50h], r15d
0x18000f498  jbe     short loc_18000F4E7
0x18000f49a  mov     rax, [r12]
0x18000f49e  lea     rdx, [rbp+57h+var_C0]
0x18000f4a2  xorps   xmm0, xmm0
0x18000f4a5  mov     rcx, r12
0x18000f4a8  movups  xmmword ptr [rbp+57h+var_C0], xmm0
0x18000f4ac  mov     rax, [rax+30h]
0x18000f4b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4b5  mov     ebx, eax
0x18000f4b7  test    eax, eax
0x18000f4b9  js      loc_18000F574
0x18000f4bf  movzx   r9d, word ptr [rbp+57h+var_C0+8]; unsigned __int16
0x18000f4c4  lea     rcx, [rbp+57h+var_A0]; this
0x18000f4c8  mov     r8d, [rbp+57h+var_C0]; unsigned int
0x18000f4cc  mov     edx, r15d; unsigned int
0x18000f4cf  call    ?SetIndexEntry@CASFIndexObject@@QEAAJKKG@Z; CASFIndexObject::SetIndexEntry(ulong,ulong,ushort)
0x18000f4d4  mov     ebx, eax
0x18000f4d6  test    eax, eax
0x18000f4d8  js      loc_18000F574
0x18000f4de  inc     r15d
0x18000f4e1  cmp     r15d, [rdi+50h]
0x18000f4e5  jb      short loc_18000F49A
0x18000f4e7  mov     eax, dword ptr [rbp+57h+var_50]
0x18000f4ea  lea     ecx, [rax+rax*2]
0x18000f4ed  lea     edi, ds:38h[rcx*2]
0x18000f4f4  mov     ecx, edi; unsigned __int64
0x18000f4f6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000f4fb  xor     r15d, r15d
0x18000f4fe  mov     rsi, rax
0x18000f501  test    rax, rax
0x18000f504  jnz     short loc_18000F50D
0x18000f506  mov     ebx, 8007000Eh
0x18000f50b  jmp     short loc_18000F574
0x18000f50d  mov     eax, [r13+298h]
0x18000f514  lea     rdx, [rbp+57h+var_C0]; struct CASFArchive *
0x18000f518  mov     [rbp+57h+var_A4], eax
0x18000f51b  lea     rcx, [rbp+57h+var_A0]; this
0x18000f51f  lea     rax, [rdi+rsi]
0x18000f523  mov     qword ptr [rbp+57h+var_C0], rsi
0x18000f527  mov     [rbp+57h+var_B0], rax
0x18000f52b  mov     qword ptr [rbp+57h+var_C0+8], rsi
0x18000f52f  mov     [rbp+57h+var_A8], 1
0x18000f536  call    ?Persist@CASFIndexObject@@UEAAJAEAVCASFArchive@@@Z; CASFIndexObject::Persist(CASFArchive &)
0x18000f53b  mov     rcx, [rbp+57h+hFile]; hFile
0x18000f53f  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000f543  mov     r8d, edi; nNumberOfBytesToWrite
0x18000f546  mov     [rbp+57h+NumberOfBytesWritten], r15d
0x18000f54a  mov     rdx, rsi; lpBuffer
0x18000f54d  mov     [rsp+100h+lpOverlapped], r15; lpOverlapped
0x18000f552  mov     ebx, eax
0x18000f554  call    cs:__imp_WriteFile
0x18000f55a  test    eax, eax
0x18000f55c  jz      short loc_18000F56F
0x18000f55e  mov     eax, [rbp+57h+NumberOfBytesWritten]
0x18000f561  cmp     eax, edi
0x18000f563  jb      short loc_18000F56F
0x18000f565  test    r14, r14
0x18000f568  jz      short loc_18000F574
0x18000f56a  mov     [r14], eax
0x18000f56d  jmp     short loc_18000F574
0x18000f56f  mov     ebx, 80004005h
0x18000f574  lea     rcx, [rbp+57h+var_A0]; this
0x18000f578  call    ??1CASFIndexObject@@UEAA@XZ; CASFIndexObject::~CASFIndexObject(void)
0x18000f57d  test    rsi, rsi
0x18000f580  jz      short loc_18000F58A
0x18000f582  mov     rcx, rsi; void *
0x18000f585  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f58a  mov     eax, ebx
0x18000f58c  jmp     short loc_18000F59F
0x18000f58e  cmp     [r9], r15d
0x18000f591  jz      short loc_18000F596
0x18000f593  mov     [r9], r15d
0x18000f596  xor     eax, eax
0x18000f598  jmp     short loc_18000F59F
0x18000f59a  mov     eax, 80070057h
0x18000f59f  mov     rcx, [rbp+57h+var_40]
0x18000f5a3  xor     rcx, rsp; StackCookie
0x18000f5a6  call    __security_check_cookie
0x18000f5ab  mov     rbx, [rsp+100h+arg_10]
0x18000f5b3  add     rsp, 0D0h
0x18000f5ba  pop     r15
0x18000f5bc  pop     r14
0x18000f5be  pop     r13
0x18000f5c0  pop     r12
0x18000f5c2  pop     rdi
0x18000f5c3  pop     rsi
0x18000f5c4  pop     rbp
0x18000f5c5  retn
```
