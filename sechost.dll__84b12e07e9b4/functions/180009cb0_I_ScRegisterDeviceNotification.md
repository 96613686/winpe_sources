# I_ScRegisterDeviceNotification

- ea: `0x180009cb0`
- end: `0x18000a02c`
- name: `I_ScRegisterDeviceNotification`
- size: `892`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callees

- `0x180009cb0`
- `0x18000a034`
- `0x18000a0a8`
- `0x18000a17c`
- `0x18000a1f0`
- `0x18004f91a`
- `0x18004fa50`
- `0x180051010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180009d41`
- `ntdll!RtlAllocateHeap` at `0x180009d41`
- `ntdll!RtlInitializeSRWLock` at `0x180009d5a`
- `ntdll!RtlInitializeSRWLock` at `0x180009d5a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009f6d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009f6d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009f61`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009f61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a000`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d94`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180009d85`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180009d85`

## pseudocode

```c
_DWORD *__fastcall I_ScRegisterDeviceNotification(const unsigned __int16 *a1, __int64 a2, int a3)
{
  _DWORD *v7; // r12
  DWORD LastError; // ebx
  _DWORD *Heap; // rax
  _DWORD *v10; // rdi
  char *v11; // r13
  PTP_WORK ThreadpoolWork; // rax
  __int64 v13; // rbx
  const unsigned __int16 **i; // r8
  int v15; // ecx
  int v16; // eax
  int v17; // eax
  bool v18; // zf
  _OWORD *v19; // rax
  _OWORD *v20; // rcx
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  _QWORD *v28; // rsi
  unsigned int v29; // eax
  __int64 v30; // [rsp+30h] [rbp-D0h] BYREF
  int v31; // [rsp+40h] [rbp-C0h] BYREF
  int v32; // [rsp+44h] [rbp-BCh]
  __int64 v33; // [rsp+48h] [rbp-B8h]
  _QWORD v34[50]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v35[256]; // [rsp+1E0h] [rbp+E0h] BYREF

  memset_0(&v31, 0, 0x1A0u);
  v30 = 0;
  memset_0(v35, 0, sizeof(v35));
  if ( !(unsigned int)ResolveCfgmgr32Imports() )
    return 0;
  v7 = 0;
  LastError = 8;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x48u);
  v10 = Heap;
  if ( Heap )
  {
    v11 = (char *)(Heap + 2);
    RtlInitializeSRWLock(Heap + 2);
    *v10 = 1450748877;
    v10[10] = a3;
    v10[4] = 1;
    v10[5] = 1;
    ThreadpoolWork = CreateThreadpoolWork(DeferredUnregisterCallback, v10, 0);
    *((_QWORD *)v10 + 8) = ThreadpoolWork;
    if ( !ThreadpoolWork )
    {
      LastError = GetLastError();
LABEL_43:
      DereferenceClientContext(v10);
      goto LABEL_44;
    }
    v13 = 3;
    if ( (a3 & 3) == 1 )
    {
      if ( hMem )
      {
        for ( i = (const unsigned __int16 **)((char *)hMem + 8); i[1]; i += 12 )
        {
          if ( i[6] == a1 )
          {
            StringCchCopyW(v35, 0x100u, i[2]);
            if ( (unsigned int)I_ScValidatePnPService(0, (__int64)v35, 0, &v30) )
              break;
            *((_QWORD *)v10 + 3) = v30;
            goto LABEL_17;
          }
        }
      }
      LastError = 6;
      goto LABEL_43;
    }
    if ( (a3 & 3) != 2 )
    {
LABEL_8:
      LastError = 1004;
      goto LABEL_43;
    }
    *(_OWORD *)(v10 + 6) = *(_OWORD *)a1;
LABEL_17:
    switch ( *(_DWORD *)(a2 + 4) )
    {
      case 5:
        v31 = 416;
        v33 = 0;
        if ( (a3 & 4) != 0 )
        {
          v32 = 1;
        }
        else
        {
          v34[0] = *(_QWORD *)(a2 + 12);
          v34[1] = *(_QWORD *)(a2 + 20);
        }
        break;
      case 6:
        v34[0] = *(_QWORD *)(a2 + 16);
        v31 = 416;
        v33 = 1;
        *((_QWORD *)v10 + 7) = v34[0];
        break;
      case 7:
        v15 = *(_DWORD *)(a2 + 12) & 0x20;
        v16 = *(_DWORD *)(a2 + 12) & 0x10;
        if ( v16 && v15 )
          goto LABEL_8;
        v31 = 416;
        if ( v16 )
        {
          LODWORD(v33) = 2;
        }
        else
        {
          v17 = v33;
          if ( v15 )
            v17 = 29144274;
          LODWORD(v33) = v17;
        }
        v18 = (*(_BYTE *)(a2 + 12) & 1) == 0;
        HIDWORD(v33) = 0;
        if ( v18 )
        {
          v19 = (_OWORD *)(a2 + 16);
          v20 = v34;
          do
          {
            v21 = v19[1];
            *v20 = *v19;
            v22 = v19[2];
            v20[1] = v21;
            v23 = v19[3];
            v20[2] = v22;
            v24 = v19[4];
            v20[3] = v23;
            v25 = v19[5];
            v20[4] = v24;
            v26 = v19[6];
            v20[5] = v25;
            v27 = v19[7];
            v19 += 8;
            v20[6] = v26;
            v20[7] = v27;
            v20 += 8;
            --v13;
          }
          while ( v13 );
          *v20 = *v19;
        }
        else
        {
          v32 = 2;
        }
        break;
      default:
        LastError = 13;
        goto LABEL_43;
    }
    RtlAcquireSRWLockExclusive(v11);
    ++v10[4];
    RtlReleaseSRWLockExclusive(v11);
    v28 = v10 + 12;
    v29 = ((__int64 (__fastcall *)(int *, _DWORD *, __int64 (__fastcall *)(), unsigned __int64, _DWORD *))qword_18007C5D8)(
            &v31,
            v10,
            DeviceNotifyEventCallback,
            (unsigned __int64)v35 & -(__int64)(v35[0] != 0),
            v10 + 12);
    LastError = ((__int64 (__fastcall *)(_QWORD, __int64))qword_18007C5E0)(v29, 1066);
    if ( LastError )
    {
      *v28 = 0;
      DereferenceClientContext(v10);
    }
    else if ( (unsigned __int64)(*v28 - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = 1066;
      *v28 = 0;
    }
    else
    {
      v7 = v10;
    }
    goto LABEL_43;
  }
LABEL_44:
  SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x180009cb0  push    rbp
0x180009cb2  push    rbx
0x180009cb3  push    rsi
0x180009cb4  push    rdi
0x180009cb5  push    r12
0x180009cb7  push    r13
0x180009cb9  push    r14
0x180009cbb  push    r15
0x180009cbd  lea     rbp, [rsp-2F8h]
0x180009cc5  sub     rsp, 3F8h
0x180009ccc  mov     rax, cs:__security_cookie
0x180009cd3  xor     rax, rsp
0x180009cd6  mov     [rbp+330h+var_50], rax
0x180009cdd  mov     r14d, r8d
0x180009ce0  mov     rsi, rdx
0x180009ce3  mov     r15, rcx
0x180009ce6  xor     edx, edx; Val
0x180009ce8  mov     r8d, 1A0h; Size
0x180009cee  lea     rcx, [rsp+430h+var_3F0]; void *
0x180009cf3  call    memset_0
0x180009cf8  xor     edx, edx; Val
0x180009cfa  mov     [rsp+430h+var_400], 0
0x180009d03  mov     r8d, 200h; Size
0x180009d09  lea     rcx, [rbp+330h+var_250]; void *
0x180009d10  call    memset_0
0x180009d15  call    ResolveCfgmgr32Imports
0x180009d1a  test    eax, eax
0x180009d1c  jnz     short loc_180009D25
0x180009d1e  xor     eax, eax
0x180009d20  jmp     loc_18000A009
0x180009d25  mov     rcx, gs:60h
0x180009d2e  xor     r12d, r12d
0x180009d31  mov     rcx, [rcx+30h]; HeapHandle
0x180009d35  lea     ebx, [r12+8]
0x180009d3a  mov     edx, ebx; Flags
0x180009d3c  lea     r8d, [r12+48h]; Size
0x180009d41  call    cs:__imp_RtlAllocateHeap
0x180009d47  mov     rdi, rax
0x180009d4a  test    rax, rax
0x180009d4d  jz      loc_180009FFE
0x180009d53  lea     r13, [rax+8]
0x180009d57  mov     rcx, r13
0x180009d5a  call    cs:__imp_RtlInitializeSRWLock
0x180009d60  xor     r8d, r8d; pcbe
0x180009d63  mov     dword ptr [rdi], 5678ABCDh
0x180009d69  mov     rdx, rdi; pv
0x180009d6c  mov     [rdi+28h], r14d
0x180009d70  lea     rcx, DeferredUnregisterCallback; pfnwk
0x180009d77  mov     dword ptr [rdi+10h], 1
0x180009d7e  mov     dword ptr [rdi+14h], 1
0x180009d85  call    cs:__imp_CreateThreadpoolWork
0x180009d8b  mov     [rdi+40h], rax
0x180009d8f  test    rax, rax
0x180009d92  jnz     short loc_180009DA1
0x180009d94  call    cs:__imp_GetLastError
0x180009d9a  mov     ebx, eax
0x180009d9c  jmp     loc_180009FF6
0x180009da1  mov     eax, r14d
0x180009da4  mov     ebx, 3
0x180009da9  and     eax, ebx
0x180009dab  sub     eax, 1
0x180009dae  jz      short loc_180009DCD
0x180009db0  cmp     eax, 1
0x180009db3  jz      short loc_180009DBF
0x180009db5  mov     ebx, 3ECh
0x180009dba  jmp     loc_180009FF6
0x180009dbf  movups  xmm0, xmmword ptr [r15]
0x180009dc3  xor     r15d, r15d
0x180009dc6  movdqu  xmmword ptr [rdi+18h], xmm0
0x180009dcb  jmp     short loc_180009E36
0x180009dcd  mov     r8, cs:hMem
0x180009dd4  test    r8, r8
0x180009dd7  jz      loc_180009FF1
0x180009ddd  add     r8, 8
0x180009de1  cmp     [r8+8], r12
0x180009de5  jz      loc_180009FF1
0x180009deb  cmp     [r8+30h], r15
0x180009def  jz      short loc_180009DF7
0x180009df1  add     r8, 60h ; '`'
0x180009df5  jmp     short loc_180009DE1
0x180009df7  mov     r8, [r8+10h]; unsigned __int16 *
0x180009dfb  lea     rcx, [rbp+330h+var_250]; unsigned __int16 *
0x180009e02  mov     edx, 100h; unsigned __int64
0x180009e07  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009e0c  lea     r9, [rsp+430h+var_400]
0x180009e11  xor     r8d, r8d
0x180009e14  lea     rdx, [rbp+330h+var_250]
0x180009e1b  xor     ecx, ecx
0x180009e1d  call    I_ScValidatePnPService
0x180009e22  xor     r15d, r15d
0x180009e25  test    eax, eax
0x180009e27  jnz     loc_180009FF1
0x180009e2d  mov     rax, [rsp+430h+var_400]
0x180009e32  mov     [rdi+18h], rax
0x180009e36  mov     ecx, [rsi+4]
0x180009e39  sub     ecx, 5
0x180009e3c  jz      loc_180009F2F
0x180009e42  sub     ecx, 1
0x180009e45  jz      loc_180009F0F
0x180009e4b  cmp     ecx, 1
0x180009e4e  jz      short loc_180009E5A
0x180009e50  mov     ebx, 0Dh
0x180009e55  jmp     loc_180009FF6
0x180009e5a  mov     eax, [rsi+0Ch]
0x180009e5d  mov     ecx, eax
0x180009e5f  and     ecx, 20h
0x180009e62  and     eax, 10h
0x180009e65  jz      short loc_180009E6F
0x180009e67  test    ecx, ecx
0x180009e69  jnz     loc_180009DB5
0x180009e6f  mov     [rsp+430h+var_3F0], 1A0h
0x180009e77  mov     r8d, 2
0x180009e7d  test    eax, eax
0x180009e7f  jz      short loc_180009E88
0x180009e81  mov     dword ptr [rsp+430h+var_3E8], r8d
0x180009e86  jmp     short loc_180009E9A
0x180009e88  mov     eax, dword ptr [rsp+430h+var_3E8]
0x180009e8c  test    ecx, ecx
0x180009e8e  mov     edx, 1BCB4D2h
0x180009e93  cmovnz  eax, edx
0x180009e96  mov     dword ptr [rsp+430h+var_3E8], eax
0x180009e9a  test    byte ptr [rsi+0Ch], 1
0x180009e9e  mov     dword ptr [rsp+430h+var_3E8+4], r15d
0x180009ea3  jz      short loc_180009EAF
0x180009ea5  mov     [rsp+430h+var_3EC], r8d
0x180009eaa  jmp     loc_180009F5E
0x180009eaf  lea     rax, [rsi+10h]
0x180009eb3  mov     edx, 80h
0x180009eb8  lea     rcx, [rsp+430h+var_3E0]
0x180009ebd  movups  xmm0, xmmword ptr [rax]
0x180009ec0  movups  xmm1, xmmword ptr [rax+10h]
0x180009ec4  movups  xmmword ptr [rcx], xmm0
0x180009ec7  movups  xmm0, xmmword ptr [rax+20h]
0x180009ecb  movups  xmmword ptr [rcx+10h], xmm1
0x180009ecf  movups  xmm1, xmmword ptr [rax+30h]
0x180009ed3  movups  xmmword ptr [rcx+20h], xmm0
0x180009ed7  movups  xmm0, xmmword ptr [rax+40h]
0x180009edb  movups  xmmword ptr [rcx+30h], xmm1
0x180009edf  movups  xmm1, xmmword ptr [rax+50h]
0x180009ee3  movups  xmmword ptr [rcx+40h], xmm0
0x180009ee7  movups  xmm0, xmmword ptr [rax+60h]
0x180009eeb  movups  xmmword ptr [rcx+50h], xmm1
0x180009eef  movups  xmm1, xmmword ptr [rax+70h]
0x180009ef3  add     rax, rdx
0x180009ef6  movups  xmmword ptr [rcx+60h], xmm0
0x180009efa  movups  xmmword ptr [rcx+70h], xmm1
0x180009efe  add     rcx, rdx
0x180009f01  sub     rbx, 1
0x180009f05  jnz     short loc_180009EBD
0x180009f07  movups  xmm0, xmmword ptr [rax]
0x180009f0a  movups  xmmword ptr [rcx], xmm0
0x180009f0d  jmp     short loc_180009F5E
0x180009f0f  mov     rax, [rsi+10h]
0x180009f13  mov     [rsp+430h+var_3E0], rax
0x180009f18  mov     [rsp+430h+var_3F0], 1A0h
0x180009f20  mov     [rsp+430h+var_3E8], 1
0x180009f29  mov     [rdi+38h], rax
0x180009f2d  jmp     short loc_180009F5E
0x180009f2f  mov     [rsp+430h+var_3F0], 1A0h
0x180009f37  mov     [rsp+430h+var_3E8], r12
0x180009f3c  test    r14b, 4
0x180009f40  jz      short loc_180009F4C
0x180009f42  mov     [rsp+430h+var_3EC], 1
0x180009f4a  jmp     short loc_180009F5E
0x180009f4c  mov     rax, [rsi+0Ch]
0x180009f50  mov     [rsp+430h+var_3E0], rax
0x180009f55  mov     rax, [rsi+14h]
0x180009f59  mov     [rsp+430h+var_3D8], rax
0x180009f5e  mov     rcx, r13
0x180009f61  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180009f67  inc     dword ptr [rdi+10h]
0x180009f6a  mov     rcx, r13
0x180009f6d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180009f73  movzx   ecx, [rbp+330h+var_250]
0x180009f7a  lea     rax, [rbp+330h+var_250]
0x180009f81  neg     cx
0x180009f84  lea     rsi, [rdi+30h]
0x180009f88  lea     r8, DeviceNotifyEventCallback
0x180009f8f  mov     [rsp+430h+var_410], rsi
0x180009f94  sbb     r9, r9
0x180009f97  lea     rcx, [rsp+430h+var_3F0]
0x180009f9c  and     r9, rax
0x180009f9f  mov     rdx, rdi
0x180009fa2  mov     rax, cs:qword_18007C5D8
0x180009fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fae  mov     ecx, eax
0x180009fb0  mov     r14d, 42Ah
0x180009fb6  mov     rax, cs:qword_18007C5E0
0x180009fbd  mov     edx, r14d
0x180009fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fc5  mov     ebx, eax
0x180009fc7  test    eax, eax
0x180009fc9  jnz     short loc_180009FE4
0x180009fcb  mov     rax, [rsi]
0x180009fce  dec     rax
0x180009fd1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009fd5  ja      short loc_180009FDC
0x180009fd7  mov     r12, rdi
0x180009fda  jmp     short loc_180009FF6
0x180009fdc  mov     ebx, r14d
0x180009fdf  mov     [rsi], r15
0x180009fe2  jmp     short loc_180009FF6
0x180009fe4  mov     rcx, rdi; P
0x180009fe7  mov     [rsi], r15
0x180009fea  call    DereferenceClientContext
0x180009fef  jmp     short loc_180009FF6
0x180009ff1  mov     ebx, 6
0x180009ff6  mov     rcx, rdi; P
0x180009ff9  call    DereferenceClientContext
0x180009ffe  mov     ecx, ebx; dwErrCode
0x18000a000  call    cs:__imp_SetLastError
0x18000a006  mov     rax, r12
0x18000a009  mov     rcx, [rbp+330h+var_50]
0x18000a010  xor     rcx, rsp; StackCookie
0x18000a013  call    __security_check_cookie
0x18000a018  add     rsp, 3F8h
0x18000a01f  pop     r15
0x18000a021  pop     r14
0x18000a023  pop     r13
0x18000a025  pop     r12
0x18000a027  pop     rdi
0x18000a028  pop     rsi
0x18000a029  pop     rbx
0x18000a02a  pop     rbp
0x18000a02b  retn
```
