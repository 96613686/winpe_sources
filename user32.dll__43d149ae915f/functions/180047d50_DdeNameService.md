# DdeNameService

- ea: `0x180047d50`
- end: `0x180047f7b`
- name: `DdeNameService`
- size: `555`
- prototype: `HDDEDATA __stdcall(DWORD idInst, HSZ hsz1, HSZ hsz2, UINT afCmd)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180047d50`
- `0x18004812c`
- `0x1800481b8`
- `0x1800481f4`
- `0x18004825c`
- `0x180048320`
- `0x1800483d4`
- `0x18006e074`

## import_xrefs

- `win32u!NtUserUpdateInstance` at `0x180047f21`
- `win32u!NtUserUpdateInstance` at `0x180047f4a`
- `win32u!NtUserUpdateInstance` at `0x180047f21`
- `win32u!NtUserUpdateInstance` at `0x180047f4a`
- `ntdll!RtlEnterCriticalSection` at `0x180047d75`
- `ntdll!RtlEnterCriticalSection` at `0x180047e52`
- `ntdll!RtlEnterCriticalSection` at `0x18009e09e`
- `ntdll!RtlEnterCriticalSection` at `0x180047d75`
- `ntdll!RtlEnterCriticalSection` at `0x180047e52`
- `ntdll!RtlEnterCriticalSection` at `0x18009e09e`
- `ntdll!RtlLeaveCriticalSection` at `0x180047e3b`
- `ntdll!RtlLeaveCriticalSection` at `0x180047e67`
- `ntdll!RtlLeaveCriticalSection` at `0x18009e087`
- `ntdll!RtlLeaveCriticalSection` at `0x180047e3b`
- `ntdll!RtlLeaveCriticalSection` at `0x180047e67`
- `ntdll!RtlLeaveCriticalSection` at `0x18009e087`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180047e00`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180047e00`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18009e07e`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18009e07e`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180047e5b`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18009e0a7`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180047e5b`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18009e0a7`

## pseudocode

```c
HDDEDATA __stdcall DdeNameService(DWORD idInst, HSZ hsz1, HSZ hsz2, UINT afCmd)
{
  void *v4; // rbx
  char v5; // si
  unsigned int v8; // ecx
  struct tagCL_INSTANCE_INFO *v9; // rdi
  __int64 v10; // rbx
  int v11; // esi
  __int16 *v12; // r9
  __int16 *v13; // rcx
  _WORD *v14; // rax
  _WORD *v15; // rbx
  unsigned __int16 v16; // bx
  unsigned int v18; // edx
  __int16 j; // ax
  int v20; // r8d
  __int64 v21; // rcx
  int v22; // r8d
  __int64 v23; // rcx
  unsigned __int16 *i; // rsi
  unsigned __int16 v25; // bx
  _WORD *v26; // rcx

  v4 = (void *)(int)idInst;
  v5 = afCmd;
  RtlEnterCriticalSection(&gcsDDEML);
  v9 = ValidateInstance(v4);
  if ( !v9 )
  {
    BestSetLastDDEMLError(v8);
    goto LABEL_16;
  }
  if ( hsz1 && !ValidateHSZ(hsz1) || hsz2 )
    goto LABEL_18;
  if ( (v5 & 4) != 0 )
  {
    v20 = *((_DWORD *)v9 + 14);
    if ( (v20 & 0x20) == 0 )
    {
      v21 = *((_QWORD *)v9 + 1);
      *((_DWORD *)v9 + 14) = v20 | 0x20;
      NtUserUpdateInstance(v21, (char *)v9 + 24);
    }
  }
  if ( (v5 & 8) != 0 )
  {
    v22 = *((_DWORD *)v9 + 14);
    if ( (v22 & 0x20) != 0 )
    {
      v23 = *((_QWORD *)v9 + 1);
      *((_DWORD *)v9 + 14) = v22 & 0xFFFFFFDF;
      NtUserUpdateInstance(v23, (char *)v9 + 24);
    }
  }
  v10 = 1;
  if ( (v5 & 3) == 0 )
    goto LABEL_14;
  if ( (*((_BYTE *)v9 + 56) & 0x10) != 0 )
  {
    v18 = 16388;
    goto LABEL_25;
  }
  v11 = v5 & 1;
  if ( !hsz1 )
  {
    if ( !v11 )
    {
      for ( i = (unsigned __int16 *)*((_QWORD *)v9 + 10); *i; ++i )
      {
        v25 = LocalToGlobalAtom(*i);
        DeleteAtom(*i);
        RtlLeaveCriticalSection(&gcsDDEML);
        RegisterService(0, v25, *((HWND *)v9 + 4));
        RtlEnterCriticalSection(&gcsDDEML);
        GlobalDeleteAtom(v25);
      }
      v26 = (_WORD *)*((_QWORD *)v9 + 10);
      *((_WORD *)v9 + 44) = 1;
      *v26 = 0;
      goto LABEL_13;
    }
LABEL_18:
    v18 = 16390;
LABEL_25:
    SetLastDDEMLError(v9, v18);
    goto LABEL_16;
  }
  v12 = (__int16 *)*((_QWORD *)v9 + 10);
  v13 = v12;
  if ( v11 )
  {
    v14 = LocalReAlloc(v12, 2LL * (unsigned __int16)++*((_WORD *)v9 + 44), 0x42u);
    v15 = v14;
    if ( v14 )
    {
      *((_QWORD *)v9 + 10) = v14;
      IncLocalAtomCount((unsigned __int16)hsz1);
      v15[*((unsigned __int16 *)v9 + 44) - 2] = (_WORD)hsz1;
      v15[*((unsigned __int16 *)v9 + 44) - 1] = 0;
LABEL_12:
      v16 = LocalToGlobalAtom((unsigned __int16)hsz1);
      RtlLeaveCriticalSection(&gcsDDEML);
      RegisterService(v11, v16, *((HWND *)v9 + 4));
      RtlEnterCriticalSection(&gcsDDEML);
      GlobalDeleteAtom(v16);
LABEL_13:
      v10 = 1;
      goto LABEL_14;
    }
    SetLastDDEMLError(v9, 0x4008u);
    --*((_WORD *)v9 + 44);
LABEL_16:
    v10 = 0;
    goto LABEL_14;
  }
  for ( j = *v12; j && j != (_WORD)hsz1; j = *v13 )
    ++v13;
  if ( *v13 )
  {
    *v13 = v12[(unsigned __int16)--*((_WORD *)v9 + 44) - 1];
    *(_WORD *)(*((_QWORD *)v9 + 10) + 2LL * *((unsigned __int16 *)v9 + 44) - 2) = 0;
    goto LABEL_12;
  }
LABEL_14:
  RtlLeaveCriticalSection(&gcsDDEML);
  return (HDDEDATA)v10;
}

```

## disassembly

```asm
0x180047d50  push    rbx
0x180047d52  push    rbp
0x180047d53  push    rsi
0x180047d54  push    rdi
0x180047d55  push    r12
0x180047d57  push    r14
0x180047d59  push    r15
0x180047d5b  sub     rsp, 20h
0x180047d5f  movsxd  rbx, ecx
0x180047d62  lea     r12, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION gcsDDEML
0x180047d69  mov     rcx, r12; CriticalSection
0x180047d6c  mov     esi, r9d
0x180047d6f  mov     r14, r8
0x180047d72  mov     rbp, rdx
0x180047d75  call    cs:__imp_RtlEnterCriticalSection
0x180047d7b  mov     rcx, rbx; void *
0x180047d7e  call    ?ValidateInstance@@YAPEAUtagCL_INSTANCE_INFO@@PEAX@Z; ValidateInstance(void *)
0x180047d83  xor     r15d, r15d
0x180047d86  mov     rdi, rax
0x180047d89  test    rax, rax
0x180047d8c  jz      loc_180047EB1
0x180047d92  test    rbp, rbp
0x180047d95  jnz     loc_180047E9A
0x180047d9b  test    r14, r14
0x180047d9e  jnz     loc_180047EAA
0x180047da4  test    sil, 4
0x180047da8  jnz     loc_180047F03
0x180047dae  test    sil, 8
0x180047db2  jnz     loc_180047F2C
0x180047db8  mov     r14d, 1
0x180047dbe  mov     ebx, r14d
0x180047dc1  test    sil, 3
0x180047dc5  jz      loc_180047E64
0x180047dcb  test    byte ptr [rdi+38h], 10h
0x180047dcf  jnz     loc_180047EF4
0x180047dd5  and     esi, r14d
0x180047dd8  test    rbp, rbp
0x180047ddb  jz      loc_180047F55
0x180047de1  mov     r9, [rdi+50h]
0x180047de5  mov     rcx, r9; hMem
0x180047de8  test    esi, esi
0x180047dea  jz      loc_180047EB8
0x180047df0  add     [rdi+58h], r14w
0x180047df5  lea     r8d, [r14+41h]; uFlags
0x180047df9  movzx   edx, word ptr [rdi+58h]
0x180047dfd  add     rdx, rdx; uBytes
0x180047e00  call    cs:__imp_LocalReAlloc
0x180047e06  mov     rbx, rax
0x180047e09  test    rax, rax
0x180047e0c  jz      short loc_180047E7F
0x180047e0e  movzx   ecx, bp; unsigned __int16
0x180047e11  mov     [rdi+50h], rax
0x180047e15  call    ?IncLocalAtomCount@@YAGG@Z; IncLocalAtomCount(ushort)
0x180047e1a  movzx   eax, word ptr [rdi+58h]
0x180047e1e  mov     [rbx+rax*2-4], bp
0x180047e23  movzx   ecx, word ptr [rdi+58h]
0x180047e27  mov     [rbx+rcx*2-2], r15w
0x180047e2d  movzx   ecx, bp; unsigned __int16
0x180047e30  call    ?LocalToGlobalAtom@@YAGG@Z; LocalToGlobalAtom(ushort)
0x180047e35  mov     rcx, r12; CriticalSection
0x180047e38  movzx   ebx, ax
0x180047e3b  call    cs:__imp_RtlLeaveCriticalSection
0x180047e41  mov     r8, [rdi+20h]; HWND
0x180047e45  movzx   edx, bx; unsigned __int16
0x180047e48  mov     ecx, esi; int
0x180047e4a  call    ?RegisterService@@YAXHGPEAUHWND__@@@Z; RegisterService(int,ushort,HWND__ *)
0x180047e4f  mov     rcx, r12; CriticalSection
0x180047e52  call    cs:__imp_RtlEnterCriticalSection
0x180047e58  movzx   ecx, bx; nAtom
0x180047e5b  call    cs:__imp_GlobalDeleteAtom
0x180047e61  mov     rbx, r14
0x180047e64  mov     rcx, r12; CriticalSection
0x180047e67  call    cs:__imp_RtlLeaveCriticalSection
0x180047e6d  mov     rax, rbx
0x180047e70  add     rsp, 20h
0x180047e74  pop     r15
0x180047e76  pop     r14
0x180047e78  pop     r12
0x180047e7a  pop     rdi
0x180047e7b  pop     rsi
0x180047e7c  pop     rbp
0x180047e7d  pop     rbx
0x180047e7e  retn
0x180047e7f  mov     edx, 4008h; unsigned int
0x180047e84  mov     rcx, rdi; struct tagCL_INSTANCE_INFO *
0x180047e87  call    ?SetLastDDEMLError@@YAXPEAUtagCL_INSTANCE_INFO@@K@Z; SetLastDDEMLError(tagCL_INSTANCE_INFO *,ulong)
0x180047e8c  mov     eax, 0FFFFh
0x180047e91  add     [rdi+58h], ax
0x180047e95  mov     rbx, r15
0x180047e98  jmp     short loc_180047E64
0x180047e9a  mov     rcx, rbp; HSZ
0x180047e9d  call    ?ValidateHSZ@@YAKPEAUHSZ__@@@Z; ValidateHSZ(HSZ__ *)
0x180047ea2  test    eax, eax
0x180047ea4  jnz     loc_180047D9B
0x180047eaa  mov     edx, 4006h
0x180047eaf  jmp     short loc_180047EF9
0x180047eb1  call    ?BestSetLastDDEMLError@@YAXK@Z; BestSetLastDDEMLError(ulong)
0x180047eb6  jmp     short loc_180047E95
0x180047eb8  movzx   eax, word ptr [r9]
0x180047ebc  test    ax, ax
0x180047ebf  jnz     loc_180047F66
0x180047ec5  cmp     [rcx], r15w
0x180047ec9  jz      short loc_180047E64
0x180047ecb  mov     eax, 0FFFFh
0x180047ed0  add     [rdi+58h], ax
0x180047ed4  movzx   eax, word ptr [rdi+58h]
0x180047ed8  movzx   eax, word ptr [r9+rax*2-2]
0x180047ede  mov     [rcx], ax
0x180047ee1  movzx   edx, word ptr [rdi+58h]
0x180047ee5  mov     rcx, [rdi+50h]
0x180047ee9  mov     [rcx+rdx*2-2], r15w
0x180047eef  jmp     loc_180047E2D
0x180047ef4  mov     edx, 4004h; unsigned int
0x180047ef9  mov     rcx, rdi; struct tagCL_INSTANCE_INFO *
0x180047efc  call    ?SetLastDDEMLError@@YAXPEAUtagCL_INSTANCE_INFO@@K@Z; SetLastDDEMLError(tagCL_INSTANCE_INFO *,ulong)
0x180047f01  jmp     short loc_180047E95
0x180047f03  mov     r8d, [rdi+38h]
0x180047f07  test    r8b, 20h
0x180047f0b  jnz     loc_180047DAE
0x180047f11  mov     rcx, [rdi+8]
0x180047f15  lea     rdx, [rdi+18h]
0x180047f19  or      r8d, 20h
0x180047f1d  mov     [rdi+38h], r8d
0x180047f21  call    cs:__imp_NtUserUpdateInstance
0x180047f27  jmp     loc_180047DAE
0x180047f2c  mov     r8d, [rdi+38h]
0x180047f30  test    r8b, 20h
0x180047f34  jz      loc_180047DB8
0x180047f3a  mov     rcx, [rdi+8]
0x180047f3e  lea     rdx, [rdi+18h]
0x180047f42  and     r8d, 0FFFFFFDFh
0x180047f46  mov     [rdi+38h], r8d
0x180047f4a  call    cs:__imp_NtUserUpdateInstance
0x180047f50  jmp     loc_180047DB8
0x180047f55  test    esi, esi
0x180047f57  jnz     loc_180047EAA
0x180047f5d  mov     rsi, [rdi+50h]
0x180047f61  jmp     loc_18009E0B1
0x180047f66  cmp     ax, bp
0x180047f69  jz      loc_180047EC5
0x180047f6f  add     rcx, 2
0x180047f73  movzx   eax, word ptr [rcx]
0x180047f76  jmp     loc_180047EBC
0x18009e070  movzx   ecx, ax; unsigned __int16
0x18009e073  call    ?LocalToGlobalAtom@@YAGG@Z; LocalToGlobalAtom(ushort)
0x18009e078  movzx   ecx, word ptr [rsi]; nAtom
0x18009e07b  movzx   ebx, ax
0x18009e07e  call    cs:__imp_DeleteAtom
0x18009e084  mov     rcx, r12; CriticalSection
0x18009e087  call    cs:__imp_RtlLeaveCriticalSection
0x18009e08d  mov     r8, [rdi+20h]; HWND
0x18009e091  movzx   edx, bx; unsigned __int16
0x18009e094  xor     ecx, ecx; int
0x18009e096  call    ?RegisterService@@YAXHGPEAUHWND__@@@Z; RegisterService(int,ushort,HWND__ *)
0x18009e09b  mov     rcx, r12; CriticalSection
0x18009e09e  call    cs:__imp_RtlEnterCriticalSection
0x18009e0a4  movzx   ecx, bx; nAtom
0x18009e0a7  call    cs:__imp_GlobalDeleteAtom
0x18009e0ad  lea     rsi, [rsi+2]
0x18009e0b1  movzx   eax, word ptr [rsi]
0x18009e0b4  test    ax, ax
0x18009e0b7  jnz     short loc_18009E070
0x18009e0b9  mov     rcx, [rdi+50h]
0x18009e0bd  mov     [rdi+58h], r14w
0x18009e0c2  mov     [rcx], r15w
0x18009e0c6  jmp     loc_180047E61
```
