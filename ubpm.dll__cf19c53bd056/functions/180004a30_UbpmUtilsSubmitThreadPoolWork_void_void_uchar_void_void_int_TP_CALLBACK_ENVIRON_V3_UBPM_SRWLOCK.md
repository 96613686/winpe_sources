# UbpmUtilsSubmitThreadPoolWork(void (*)(void *,uchar,void *),void *,int,_TP_CALLBACK_ENVIRON_V3 *,_UBPM_SRWLOCK *)

- ea: `0x180004a30`
- end: `0x180004c65`
- name: `?UbpmUtilsSubmitThreadPoolWork@@YAKP6AXPEAXE0@Z0HPEAU_TP_CALLBACK_ENVIRON_V3@@PEAU_UBPM_SRWLOCK@@@Z`
- size: `565`
- prototype: `unsigned int(void (*)(void *, unsigned __int8, void *), void *, int, struct _TP_CALLBACK_ENVIRON_V3 *, struct _UBPM_SRWLOCK *)`
- caller_count: `15`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002f60`
- `0x180004058`
- `0x180004194`
- `0x1800049b4`
- `0x1800057b0`
- `0x18000ae40`
- `0x18000c650`
- `0x18001311c`
- `0x1800138e0`
- `0x180016eb0`
- `0x180021060`
- `0x18002e964`
- `0x180034350`
- `0x180034380`
- `0x18003625c`

## callees

- `0x180004a30`
- `0x180032e38`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180004b2d`
- `ntdll!RtlFreeHeap` at `0x180004b2d`
- `ntdll!RtlTryAcquireSRWLockShared` at `0x180004aa7`
- `ntdll!RtlTryAcquireSRWLockShared` at `0x180004aa7`
- `ntdll!RtlAllocateHeap` at `0x180004a60`
- `ntdll!RtlAllocateHeap` at `0x180004a60`
- `ntdll!RtlReleaseSRWLockShared` at `0x180004c5a`
- `ntdll!RtlReleaseSRWLockShared` at `0x180004c5a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180004ad7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180004ad7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180004b05`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180004b05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c2c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b7d`

## pseudocode

```c
__int64 __fastcall UbpmUtilsSubmitThreadPoolWork(
        void (*a1)(void *, unsigned __int8, void *),
        void *a2,
        char a3,
        struct _TP_CALLBACK_ENVIRON_V3 *a4,
        struct _UBPM_SRWLOCK *a5)
{
  _DWORD *Heap; // rbx
  struct _TP_CALLBACK_ENVIRON_V3 *v10; // rbp
  char v11; // r14
  struct _UBPM_SRWLOCK *v12; // r15
  struct _TP_WORK *ThreadpoolWork; // rcx
  char v14; // si
  DWORD LastError; // edi
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  DWORD v19; // ebx

  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x30u);
  if ( Heap )
  {
    v10 = &g_CallbackEnv;
    v11 = 0;
    v12 = (struct _UBPM_SRWLOCK *)&g_TpSubmitLock;
    if ( a4 )
    {
      v12 = a5;
      v10 = a4;
    }
    if ( v12 )
    {
      if ( !(unsigned __int8)RtlTryAcquireSRWLockShared(v12) )
      {
        LastError = 1235;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, 1235);
LABEL_14:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        return LastError;
      }
      v11 = 1;
    }
    if ( a4 || g_pThreadpool )
    {
      ThreadpoolWork = CreateThreadpoolWork(UbpmUtilsWorkCallback, Heap, v10);
      if ( ThreadpoolWork )
      {
        v14 = *((_BYTE *)Heap + 24) ^ a3;
        *Heap = 1886667349;
        *((_BYTE *)Heap + 24) ^= v14 & 1;
        *((_QWORD *)Heap + 1) = a2;
        *((_QWORD *)Heap + 2) = a1;
        Heap = 0;
        SubmitThreadpoolWork(ThreadpoolWork);
        LastError = 0;
        goto LABEL_11;
      }
      LastError = GetLastError();
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_11;
      v18 = 22;
    }
    else
    {
      LastError = 1115;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_11;
      v18 = 21;
    }
    WPP_SF_d(v17[2], v18, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, LastError);
LABEL_11:
    if ( v11 )
      RtlReleaseSRWLockShared(v12);
    if ( !Heap )
      return LastError;
    goto LABEL_14;
  }
  SetLastError(8u);
  v19 = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, v19);
  return v19;
}

```

## disassembly

```asm
0x180004a30  push    rbx
0x180004a32  push    rsi
0x180004a33  push    rdi
0x180004a34  push    r12
0x180004a36  push    r13
0x180004a38  sub     rsp, 20h
0x180004a3c  mov     r13, rcx
0x180004a3f  mov     esi, r8d
0x180004a42  mov     rcx, gs:60h
0x180004a4b  mov     r12, rdx
0x180004a4e  mov     edx, 8; Flags
0x180004a53  mov     r8d, 30h ; '0'; Size
0x180004a59  mov     rdi, r9
0x180004a5c  mov     rcx, [rcx+30h]; HeapHandle
0x180004a60  call    cs:__imp_RtlAllocateHeap
0x180004a66  mov     rbx, rax
0x180004a69  test    rax, rax
0x180004a6c  jz      loc_180004B78
0x180004a72  mov     [rsp+48h+arg_0], rbp
0x180004a77  lea     rbp, ?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv
0x180004a7e  mov     [rsp+48h+arg_8], r14
0x180004a83  xor     r14b, r14b
0x180004a86  test    rdi, rdi
0x180004a89  mov     [rsp+48h+arg_10], r15
0x180004a8e  lea     r15, ?g_TpSubmitLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_TpSubmitLock
0x180004a95  cmovnz  r15, [rsp+48h+arg_20]
0x180004a9b  cmovnz  rbp, rdi
0x180004a9f  test    r15, r15
0x180004aa2  jz      short loc_180004AB8
0x180004aa4  mov     rcx, r15
0x180004aa7  call    cs:__imp_RtlTryAcquireSRWLockShared
0x180004aad  test    al, al
0x180004aaf  jz      loc_180004BCC
0x180004ab5  mov     r14b, 1
0x180004ab8  test    rdi, rdi
0x180004abb  jnz     short loc_180004ACA
0x180004abd  cmp     cs:?g_pThreadpool@@3PEAU_TP_POOL@@EA, rdi; _TP_POOL * g_pThreadpool
0x180004ac4  jz      loc_180004B50
0x180004aca  mov     r8, rbp; pcbe
0x180004acd  lea     rcx, ?UbpmUtilsWorkCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180004ad4  mov     rdx, rbx; pv
0x180004ad7  call    cs:__imp_CreateThreadpoolWork
0x180004add  mov     rcx, rax; pwk
0x180004ae0  test    rax, rax
0x180004ae3  jz      loc_180004C2C
0x180004ae9  xor     sil, [rbx+18h]
0x180004aed  mov     dword ptr [rbx], 70744255h
0x180004af3  and     sil, 1
0x180004af7  xor     [rbx+18h], sil
0x180004afb  mov     [rbx+8], r12
0x180004aff  mov     [rbx+10h], r13
0x180004b03  xor     ebx, ebx
0x180004b05  call    cs:__imp_SubmitThreadpoolWork
0x180004b0b  xor     edi, edi
0x180004b0d  test    r14b, r14b
0x180004b10  jnz     loc_180004C57
0x180004b16  test    rbx, rbx
0x180004b19  jz      short loc_180004B33
0x180004b1b  mov     rcx, gs:60h
0x180004b24  mov     r8, rbx; P
0x180004b27  xor     edx, edx; Flags
0x180004b29  mov     rcx, [rcx+30h]; HeapHandle
0x180004b2d  call    cs:__imp_RtlFreeHeap
0x180004b33  mov     r14, [rsp+48h+arg_8]
0x180004b38  mov     eax, edi
0x180004b3a  mov     rbp, [rsp+48h+arg_0]
0x180004b3f  mov     r15, [rsp+48h+arg_10]
0x180004b44  add     rsp, 20h
0x180004b48  pop     r13
0x180004b4a  pop     r12
0x180004b4c  pop     rdi
0x180004b4d  pop     rsi
0x180004b4e  pop     rbx
0x180004b4f  retn
0x180004b50  mov     edi, 45Bh
0x180004b55  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b5c  lea     rax, WPP_GLOBAL_Control
0x180004b63  cmp     rcx, rax
0x180004b66  jz      short loc_180004B0D
0x180004b68  test    byte ptr [rcx+1Ch], 1
0x180004b6c  jz      short loc_180004B0D
0x180004b6e  mov     edx, 15h
0x180004b73  jmp     loc_180004C14
0x180004b78  mov     ecx, 8; dwErrCode
0x180004b7d  call    cs:__imp_SetLastError
0x180004b83  call    cs:__imp_GetLastError
0x180004b89  mov     ebx, eax
0x180004b8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b92  lea     rax, WPP_GLOBAL_Control
0x180004b99  cmp     rcx, rax
0x180004b9c  jnz     short loc_180004BAC
0x180004b9e  mov     eax, ebx
0x180004ba0  add     rsp, 20h
0x180004ba4  pop     r13
0x180004ba6  pop     r12
0x180004ba8  pop     rdi
0x180004ba9  pop     rsi
0x180004baa  pop     rbx
0x180004bab  retn
0x180004bac  test    byte ptr [rcx+1Ch], 1
0x180004bb0  jz      short loc_180004B9E
0x180004bb2  mov     rcx, [rcx+10h]
0x180004bb6  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x180004bbd  mov     edx, 13h
0x180004bc2  mov     r9d, ebx
0x180004bc5  call    WPP_SF_d
0x180004bca  jmp     short loc_180004B9E
0x180004bcc  mov     edi, 4D3h
0x180004bd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bd8  lea     rax, WPP_GLOBAL_Control
0x180004bdf  cmp     rcx, rax
0x180004be2  jz      loc_180004B1B
0x180004be8  test    byte ptr [rcx+1Ch], 1
0x180004bec  jz      loc_180004B1B
0x180004bf2  mov     rcx, [rcx+10h]
0x180004bf6  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x180004bfd  mov     edx, 14h
0x180004c02  mov     r9d, edi
0x180004c05  call    WPP_SF_d
0x180004c0a  jmp     loc_180004B1B
0x180004c0f  mov     edx, 16h
0x180004c14  mov     rcx, [rcx+10h]
0x180004c18  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x180004c1f  mov     r9d, edi
0x180004c22  call    WPP_SF_d
0x180004c27  jmp     loc_180004B0D
0x180004c2c  call    cs:__imp_GetLastError
0x180004c32  mov     edi, eax
0x180004c34  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c3b  lea     rax, WPP_GLOBAL_Control
0x180004c42  cmp     rcx, rax
0x180004c45  jz      loc_180004B0D
0x180004c4b  test    byte ptr [rcx+1Ch], 1
0x180004c4f  jz      loc_180004B0D
0x180004c55  jmp     short loc_180004C0F
0x180004c57  mov     rcx, r15
0x180004c5a  call    cs:__imp_RtlReleaseSRWLockShared
0x180004c60  jmp     loc_180004B16
```
