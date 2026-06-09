# CNtSecurityDescriptor::CNtSecurityDescriptor(void *)

- ea: `0x180023900`
- end: `0x180023a4c`
- name: `??0CNtSecurityDescriptor@@QEAA@PEAX@Z`
- size: `332`
- prototype: `CNtSecurityDescriptor *(CNtSecurityDescriptor *__hidden this, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003f730`

## callees

- `0x18000a290`
- `0x18000ab30`
- `0x18001d19c`
- `0x180023900`
- `0x180023d3c`
- `0x180025548`
- `0x18002ee96`
- `0x1800442d3`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800239f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800239f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800239b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800239b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800239ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800239ca`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180023969`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180023969`

## string_xrefs

- `0x1800239c3`: `GetSecurityDescriptorControl`

## pseudocode

```c
CNtSecurityDescriptor *__fastcall CNtSecurityDescriptor::CNtSecurityDescriptor(CNtSecurityDescriptor *this, void *a2)
{
  FARPROC ProcAddress; // rax
  ULONG v5; // esi
  void *v6; // rax
  DWORD SecurityDll; // eax
  void *v9; // rax
  __int16 v10; // [rsp+40h] [rbp+8h] BYREF
  size_t Size; // [rsp+48h] [rbp+10h] BYREF
  int v12; // [rsp+50h] [rbp+18h] BYREF

  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 1;
  if ( a2 )
  {
    if ( (unsigned int)DLIsValidSecurityDescriptor(a2) )
    {
      v10 = 0;
      v12 = 0;
      ProcAddress = (FARPROC)qword_180070340;
      if ( !qword_180070340 )
      {
        SecurityDll = DLpLoadSecurityDll();
        if ( SecurityDll )
        {
          SetLastError(SecurityDll);
          goto LABEL_10;
        }
        ProcAddress = GetProcAddress(g_hInstSecurityDLL, "GetSecurityDescriptorControl");
        qword_180070340 = (__int64)ProcAddress;
        if ( !ProcAddress )
          goto LABEL_10;
      }
      if ( ((unsigned int (__fastcall *)(void *, __int16 *, int *))ProcAddress)(a2, &v10, &v12) )
      {
        if ( v10 >= 0 )
        {
          LODWORD(Size) = 0;
          DLMakeSelfRelativeSD(a2, 0, (unsigned int *)&Size);
          if ( GetLastError() == 122 )
          {
            v9 = CWin32DefaultArena::WbemMemAlloc((unsigned int)Size);
            *(_QWORD *)this = v9;
            if ( v9 )
            {
              memset_0(v9, 0, (unsigned int)Size);
              if ( (unsigned int)DLMakeSelfRelativeSD(a2, *(void **)this, (unsigned int *)&Size) )
                goto LABEL_8;
              CMUILocale::_Free(*(void **)this);
              *(_QWORD *)this = 0;
            }
          }
        }
        else
        {
          v5 = RtlLengthSecurityDescriptor(a2);
          v6 = CWin32DefaultArena::WbemMemAlloc(v5);
          *(_QWORD *)this = v6;
          if ( v6 )
          {
            memcpy_0(v6, a2, v5);
LABEL_8:
            *((_DWORD *)this + 2) = 0;
            return this;
          }
        }
      }
    }
LABEL_10:
    *((_DWORD *)this + 2) = 3;
  }
  return this;
}

```

## disassembly

```asm
0x180023900  push    rbx
0x180023902  push    rsi
0x180023903  push    rdi
0x180023904  sub     rsp, 20h
0x180023908  mov     qword ptr [rcx], 0
0x18002390f  mov     rdi, rdx
0x180023912  mov     dword ptr [rcx+8], 1
0x180023919  mov     rbx, rcx
0x18002391c  test    rdx, rdx
0x18002391f  jz      short loc_180023995
0x180023921  mov     rcx, rdx; void *
0x180023924  call    ?DLIsValidSecurityDescriptor@@YAHPEAX@Z; DLIsValidSecurityDescriptor(void *)
0x180023929  test    eax, eax
0x18002392b  jz      short loc_1800239A0
0x18002392d  xor     eax, eax
0x18002392f  mov     [rsp+38h+arg_0], ax
0x180023934  mov     [rsp+38h+arg_10], eax
0x180023938  mov     rax, cs:qword_180070340
0x18002393f  test    rax, rax
0x180023942  jz      short loc_1800239A9
0x180023944  lea     r8, [rsp+38h+arg_10]
0x180023949  mov     rcx, rdi
0x18002394c  lea     rdx, [rsp+38h+arg_0]
0x180023951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023956  test    eax, eax
0x180023958  jz      short loc_1800239A0
0x18002395a  mov     eax, 8000h
0x18002395f  mov     rcx, rdi; void *
0x180023962  test    [rsp+38h+arg_0], ax
0x180023967  jz      short loc_1800239E1
0x180023969  call    cs:__imp_RtlLengthSecurityDescriptor
0x18002396f  mov     ecx, eax; unsigned __int64
0x180023971  mov     esi, eax
0x180023973  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180023978  mov     [rbx], rax
0x18002397b  test    rax, rax
0x18002397e  jz      short loc_1800239A0
0x180023980  mov     r8d, esi; Size
0x180023983  mov     rdx, rdi; Src
0x180023986  mov     rcx, rax; void *
0x180023989  call    memcpy_0
0x18002398e  mov     dword ptr [rbx+8], 0
0x180023995  mov     rax, rbx
0x180023998  add     rsp, 20h
0x18002399c  pop     rdi
0x18002399d  pop     rsi
0x18002399e  pop     rbx
0x18002399f  retn
0x1800239a0  mov     dword ptr [rbx+8], 3
0x1800239a7  jmp     short loc_180023995
0x1800239a9  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x1800239ae  test    eax, eax
0x1800239b0  jz      short loc_1800239BC
0x1800239b2  mov     ecx, eax; dwErrCode
0x1800239b4  call    cs:__imp_SetLastError
0x1800239ba  jmp     short loc_1800239A0
0x1800239bc  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x1800239c3  lea     rdx, aGetsecuritydes_2; "GetSecurityDescriptorControl"
0x1800239ca  call    cs:__imp_GetProcAddress
0x1800239d0  mov     cs:qword_180070340, rax
0x1800239d7  test    rax, rax
0x1800239da  jz      short loc_1800239A0
0x1800239dc  jmp     loc_180023944
0x1800239e1  lea     r8, [rsp+38h+Size]; unsigned int *
0x1800239e6  mov     dword ptr [rsp+38h+Size], 0
0x1800239ee  xor     edx, edx; void *
0x1800239f0  call    ?DLMakeSelfRelativeSD@@YAHPEAX0PEAK@Z; DLMakeSelfRelativeSD(void *,void *,ulong *)
0x1800239f5  call    cs:__imp_GetLastError
0x1800239fb  cmp     eax, 7Ah ; 'z'
0x1800239fe  jnz     short loc_1800239A0
0x180023a00  mov     ecx, dword ptr [rsp+38h+Size]; unsigned __int64
0x180023a04  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180023a09  mov     [rbx], rax
0x180023a0c  test    rax, rax
0x180023a0f  jz      short loc_1800239A0
0x180023a11  mov     r8d, dword ptr [rsp+38h+Size]; Size
0x180023a16  xor     edx, edx; Val
0x180023a18  mov     rcx, rax; void *
0x180023a1b  call    memset_0
0x180023a20  mov     rdx, [rbx]; void *
0x180023a23  lea     r8, [rsp+38h+Size]; unsigned int *
0x180023a28  mov     rcx, rdi; void *
0x180023a2b  call    ?DLMakeSelfRelativeSD@@YAHPEAX0PEAK@Z; DLMakeSelfRelativeSD(void *,void *,ulong *)
0x180023a30  test    eax, eax
0x180023a32  jnz     loc_18002398E
0x180023a38  mov     rcx, [rbx]; void *
0x180023a3b  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x180023a40  mov     qword ptr [rbx], 0
0x180023a47  jmp     loc_1800239A0
```
