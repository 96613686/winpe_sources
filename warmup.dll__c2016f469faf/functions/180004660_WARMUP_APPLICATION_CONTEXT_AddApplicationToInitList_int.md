# WARMUP_APPLICATION_CONTEXT::AddApplicationToInitList(int *)

- ea: `0x180004660`
- end: `0x18000475e`
- name: `?AddApplicationToInitList@WARMUP_APPLICATION_CONTEXT@@UEAAJPEAH@Z`
- size: `254`
- prototype: `__int64 __fastcall(WARMUP_APPLICATION_CONTEXT *__hidden this, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001008`
- `0x180004660`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000474b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000474b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004678`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004678`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800046d9`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800046d9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800046f5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800046f5`

## pseudocode

```c
__int64 __fastcall WARMUP_APPLICATION_CONTEXT::AddApplicationToInitList(WARMUP_APPLICATION_CONTEXT *this, int *a2)
{
  struct _LIST_ENTRY *i; // rdi
  struct _LIST_ENTRY *Blink; // rbx
  __int64 v6; // rax
  int v7; // edx
  int v8; // ecx
  STRU *v9; // rax
  STRU *v10; // rdi
  const unsigned __int16 *v11; // rax
  int v12; // ebx
  struct _LIST_ENTRY *Flink; // rcx

  EnterCriticalSection(&WARMUP_APPLICATION_CONTEXT::sm_csAppList);
  for ( i = WARMUP_APPLICATION_CONTEXT::sm_AppListHead.Flink; i != &WARMUP_APPLICATION_CONTEXT::sm_AppListHead; i = i->Flink )
  {
    Blink = i[-2].Blink;
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 8LL))(*((_QWORD *)this + 2)) - (_QWORD)Blink;
    do
    {
      v7 = *(unsigned __int16 *)((char *)&Blink->Flink + v6);
      v8 = LOWORD(Blink->Flink) - v7;
      if ( v8 )
        break;
      Blink = (struct _LIST_ENTRY *)((char *)Blink + 2);
    }
    while ( v7 );
    if ( !v8 )
    {
      v12 = 0;
      *a2 = 1;
      goto LABEL_15;
    }
  }
  v9 = (STRU *)operator new(0x48u);
  v10 = v9;
  if ( v9 )
  {
    STRU::STRU(v9);
    v11 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 8LL))(*((_QWORD *)this + 2));
    v12 = STRU::Copy(v10, v11);
    if ( v12 >= 0 )
    {
      Flink = WARMUP_APPLICATION_CONTEXT::sm_AppListHead.Flink;
      if ( WARMUP_APPLICATION_CONTEXT::sm_AppListHead.Flink->Blink != &WARMUP_APPLICATION_CONTEXT::sm_AppListHead )
        __fastfail(3u);
      *((_QWORD *)v10 + 7) = WARMUP_APPLICATION_CONTEXT::sm_AppListHead.Flink;
      *((_QWORD *)v10 + 8) = &WARMUP_APPLICATION_CONTEXT::sm_AppListHead;
      Flink->Blink = (struct _LIST_ENTRY *)((char *)v10 + 56);
      WARMUP_APPLICATION_CONTEXT::sm_AppListHead.Flink = (struct _LIST_ENTRY *)((char *)v10 + 56);
      *a2 = 0;
    }
  }
  else
  {
    v12 = -2147024882;
  }
LABEL_15:
  LeaveCriticalSection(&WARMUP_APPLICATION_CONTEXT::sm_csAppList);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180004660  push    rbx
0x180004662  push    rbp
0x180004663  push    rsi
0x180004664  push    rdi
0x180004665  push    r14
0x180004667  sub     rsp, 20h
0x18000466b  mov     rsi, rcx
0x18000466e  mov     r14, rdx
0x180004671  lea     rcx, ?sm_csAppList@WARMUP_APPLICATION_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004678  call    cs:__imp_EnterCriticalSection
0x18000467e  mov     rdi, cs:?sm_AppListHead@WARMUP_APPLICATION_CONTEXT@@0U_LIST_ENTRY@@A; _LIST_ENTRY WARMUP_APPLICATION_CONTEXT::sm_AppListHead
0x180004685  lea     rbp, ?sm_AppListHead@WARMUP_APPLICATION_CONTEXT@@0U_LIST_ENTRY@@A; _LIST_ENTRY WARMUP_APPLICATION_CONTEXT::sm_AppListHead
0x18000468c  jmp     short loc_1800046BF
0x18000468e  mov     rcx, [rsi+10h]
0x180004692  mov     rbx, [rdi-18h]
0x180004696  mov     rax, [rcx]
0x180004699  mov     rax, [rax+8]
0x18000469d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046a2  sub     rax, rbx
0x1800046a5  movzx   ecx, word ptr [rbx]
0x1800046a8  movzx   edx, word ptr [rbx+rax]
0x1800046ac  sub     ecx, edx
0x1800046ae  jnz     short loc_1800046B8
0x1800046b0  add     rbx, 2
0x1800046b4  test    edx, edx
0x1800046b6  jnz     short loc_1800046A5
0x1800046b8  test    ecx, ecx
0x1800046ba  jz      short loc_180004715
0x1800046bc  mov     rdi, [rdi]
0x1800046bf  cmp     rdi, rbp
0x1800046c2  jnz     short loc_18000468E
0x1800046c4  mov     ecx, 48h ; 'H'; Size
0x1800046c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800046ce  mov     rdi, rax
0x1800046d1  test    rax, rax
0x1800046d4  jz      short loc_18000473F
0x1800046d6  mov     rcx, rax
0x1800046d9  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800046df  mov     rcx, [rsi+10h]
0x1800046e3  mov     rdx, [rcx]
0x1800046e6  mov     rax, [rdx+8]
0x1800046ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ef  mov     rdx, rax
0x1800046f2  mov     rcx, rdi
0x1800046f5  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800046fb  mov     ebx, eax
0x1800046fd  test    eax, eax
0x1800046ff  js      short loc_180004744
0x180004701  mov     rcx, cs:?sm_AppListHead@WARMUP_APPLICATION_CONTEXT@@0U_LIST_ENTRY@@A; _LIST_ENTRY WARMUP_APPLICATION_CONTEXT::sm_AppListHead
0x180004708  cmp     [rcx+8], rbp
0x18000470c  jz      short loc_180004720
0x18000470e  mov     ecx, 3
0x180004713  int     29h; Win8: RtlFailFast(ecx)
0x180004715  xor     ebx, ebx
0x180004717  mov     dword ptr [r14], 1
0x18000471e  jmp     short loc_180004744
0x180004720  lea     rax, [rdi+38h]
0x180004724  mov     [rax], rcx
0x180004727  mov     [rax+8], rbp
0x18000472b  mov     [rcx+8], rax
0x18000472f  mov     cs:?sm_AppListHead@WARMUP_APPLICATION_CONTEXT@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY WARMUP_APPLICATION_CONTEXT::sm_AppListHead
0x180004736  mov     dword ptr [r14], 0
0x18000473d  jmp     short loc_180004744
0x18000473f  mov     ebx, 8007000Eh
0x180004744  lea     rcx, ?sm_csAppList@WARMUP_APPLICATION_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000474b  call    cs:__imp_LeaveCriticalSection
0x180004751  mov     eax, ebx
0x180004753  add     rsp, 20h
0x180004757  pop     r14
0x180004759  pop     rdi
0x18000475a  pop     rsi
0x18000475b  pop     rbp
0x18000475c  pop     rbx
0x18000475d  retn
```
