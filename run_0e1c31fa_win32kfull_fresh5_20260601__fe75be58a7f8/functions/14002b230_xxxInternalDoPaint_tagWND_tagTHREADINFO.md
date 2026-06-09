# xxxInternalDoPaint(tagWND *,tagTHREADINFO *)

- ea: `0x14002b230`
- end: `0x14002b62f`
- name: `?xxxInternalDoPaint@@YAPEAUtagWND@@PEAU1@PEAUtagTHREADINFO@@@Z`
- size: `1023`
- prototype: `struct tagWND *__fastcall(struct tagWND *, struct tagTHREADINFO *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002ace0`
- `0x14002b230`

## callees

- `0x140021550`
- `0x14002b230`
- `0x14002b638`
- `0x14002b900`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14002b4d7`
- `ntoskrnl!KeBugCheckEx` at `0x14002b4ff`
- `ntoskrnl!KeBugCheckEx` at `0x14002b545`
- `ntoskrnl!KeBugCheckEx` at `0x14002b56d`
- `ntoskrnl!KeBugCheckEx` at `0x14002b61e`
- `ntoskrnl!KeBugCheckEx` at `0x14002b4d7`
- `ntoskrnl!KeBugCheckEx` at `0x14002b4ff`
- `ntoskrnl!KeBugCheckEx` at `0x14002b545`
- `ntoskrnl!KeBugCheckEx` at `0x14002b56d`
- `ntoskrnl!KeBugCheckEx` at `0x14002b61e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002b240`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002b341`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002b3a1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002b41e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002b48f`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002b5b6`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002b240`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002b341`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002b3a1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002b41e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002b48f`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002b5b6`
- `win32kbase!HMLockObject` at `0x14002b27d`
- `win32kbase!HMLockObject` at `0x14002b2c2`
- `win32kbase!HMLockObject` at `0x14002b27d`
- `win32kbase!HMLockObject` at `0x14002b2c2`
- `win32kbase!HMUnlockObject` at `0x14002b2d6`
- `win32kbase!HMUnlockObject` at `0x14002b381`
- `win32kbase!HMUnlockObject` at `0x14002b3e4`
- `win32kbase!HMUnlockObject` at `0x14002b5f2`
- `win32kbase!HMUnlockObject` at `0x14002b2d6`
- `win32kbase!HMUnlockObject` at `0x14002b381`
- `win32kbase!HMUnlockObject` at `0x14002b3e4`
- `win32kbase!HMUnlockObject` at `0x14002b5f2`

## pseudocode

```c
struct tagWND *__fastcall xxxInternalDoPaint(struct tagWND *a1, struct tagTHREADINFO *a2)
{
  struct tagWND *v3; // rbx
  ULONG_PTR **CurrentThreadWin32Thread; // rax
  ULONG_PTR *v5; // rcx
  struct tagWND *v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rcx
  ULONG_PTR *v9; // rax
  ULONG_PTR v10; // rdx
  ULONG_PTR *v11; // rcx
  ULONG_PTR v12; // rcx
  struct tagWND *result; // rax
  ULONG_PTR *v14; // rax
  ULONG_PTR v15; // rdx
  ULONG_PTR *v16; // rcx
  struct tagWND *v17; // rax
  __int64 v18; // rdi
  ULONG_PTR *v19; // rax
  ULONG_PTR v20; // rdx
  ULONG_PTR *v21; // rcx
  ULONG_PTR v22; // rcx
  __int64 v23; // rcx
  ULONG_PTR *v24; // rax
  __int64 v25; // rcx
  ULONG_PTR *v26; // rax
  ULONG_PTR v27; // rdx
  ULONG_PTR *v28; // rcx
  ULONG_PTR BugCheckParameter3; // [rsp+30h] [rbp-18h] BYREF
  struct tagWND *v30; // [rsp+38h] [rbp-10h]

  v3 = a1;
  CurrentThreadWin32Thread = (ULONG_PTR **)PsGetCurrentThreadWin32Thread(a1);
  if ( CurrentThreadWin32Thread )
    v5 = *CurrentThreadWin32Thread;
  else
    v5 = 0;
  BugCheckParameter3 = v5[56];
  v5[56] = (ULONG_PTR)&BugCheckParameter3;
  v30 = v3;
  if ( v3 )
    HMLockObject(v3);
  while ( 1 )
  {
    while ( 1 )
    {
      if ( !v3 )
      {
        v14 = (ULONG_PTR *)PsGetCurrentThreadWin32Thread(v5);
        if ( v14 )
          v15 = *v14;
        else
          v15 = 0;
        v16 = *(ULONG_PTR **)(v15 + 448);
        if ( v16 != &BugCheckParameter3 )
          KeBugCheckEx(0x164u, 0x3Bu, v15, (ULONG_PTR)&BugCheckParameter3, 0);
        *(_QWORD *)(v15 + 448) = *v16;
        result = (struct tagWND *)v16[1];
        if ( result )
          return (struct tagWND *)HMUnlockObject(v16[1]);
        return result;
      }
      if ( *((struct tagTHREADINFO **)v3 + 2) == a2 )
        break;
LABEL_7:
      v5 = (ULONG_PTR *)*((_QWORD *)v3 + 14);
      if ( v5 )
      {
        v17 = xxxInternalDoPaint((struct tagWND *)v5, a2);
        v18 = (__int64)v17;
        if ( v17 )
        {
          if ( v17 == v3 )
          {
            v18 = Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)&BugCheckParameter3);
            if ( BugCheckParameter3 == -1 )
              return (struct tagWND *)v18;
            v26 = (ULONG_PTR *)PsGetCurrentThreadWin32Thread(v25);
            if ( v26 )
              v27 = *v26;
            else
              v27 = 0;
            v28 = *(ULONG_PTR **)(v27 + 448);
            if ( v28 != &BugCheckParameter3 )
              KeBugCheckEx(0x164u, 0x3Bu, v27, (ULONG_PTR)&BugCheckParameter3, 0);
            *(_QWORD *)(v27 + 448) = *v28;
            v22 = v28[1];
            if ( !v22 )
              return (struct tagWND *)v18;
          }
          else
          {
            v19 = (ULONG_PTR *)PsGetCurrentThreadWin32Thread(v5);
            if ( v19 )
              v20 = *v19;
            else
              v20 = 0;
            v21 = *(ULONG_PTR **)(v20 + 448);
            if ( v21 != &BugCheckParameter3 )
              KeBugCheckEx(0x164u, 0x3Bu, v20, (ULONG_PTR)&BugCheckParameter3, 0);
            *(_QWORD *)(v20 + 448) = *v21;
            v22 = v21[1];
            if ( !v22 )
              return (struct tagWND *)v18;
          }
          HMUnlockObject(v22);
          return (struct tagWND *)v18;
        }
      }
      v3 = (struct tagWND *)*((_QWORD *)v3 + 11);
      v6 = v30;
      v30 = v3;
      if ( v3 )
        HMLockObject(v3);
      if ( v6 )
        HMUnlockObject(v6);
    }
    v7 = *((_QWORD *)v3 + 5);
    if ( (*(_BYTE *)(v7 + 27) & 2) == 0 )
      break;
    xxxCompositedPaint(v3);
    v3 = (struct tagWND *)*((_QWORD *)v3 + 11);
    Win32HM_ExchangeThreadLock<1>(v3, &BugCheckParameter3);
  }
  if ( !*(_QWORD *)(v7 + 136) && (*(_BYTE *)(v7 + 17) & 0x10) == 0 )
    goto LABEL_7;
  if ( (*(_BYTE *)(v7 + 24) & 0x20) != 0 )
  {
    while ( 1 )
    {
      v3 = (struct tagWND *)*((_QWORD *)v3 + 11);
      if ( !v3 )
        break;
      if ( *((struct tagTHREADINFO **)v3 + 2) == a2 )
      {
        v8 = *((_QWORD *)v3 + 5);
        if ( (*(_QWORD *)(v8 + 136) || (*(_BYTE *)(v8 + 17) & 0x10) != 0) && (*(_BYTE *)(v8 + 24) & 0x20) == 0 )
        {
          if ( BugCheckParameter3 == -1 )
            return v3;
          v9 = (ULONG_PTR *)PsGetCurrentThreadWin32Thread(v8);
          if ( v9 )
            v10 = *v9;
          else
            v10 = 0;
          v11 = *(ULONG_PTR **)(v10 + 448);
          if ( v11 != &BugCheckParameter3 )
            KeBugCheckEx(0x164u, 0x3Bu, v10, (ULONG_PTR)&BugCheckParameter3, 0);
          goto LABEL_25;
        }
      }
    }
  }
  v3 = (struct tagWND *)Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)&BugCheckParameter3);
  if ( BugCheckParameter3 != -1 )
  {
    v24 = (ULONG_PTR *)PsGetCurrentThreadWin32Thread(v23);
    if ( v24 )
      v10 = *v24;
    else
      v10 = 0;
    v11 = *(ULONG_PTR **)(v10 + 448);
    if ( v11 != &BugCheckParameter3 )
      KeBugCheckEx(0x164u, 0x3Bu, v10, (ULONG_PTR)&BugCheckParameter3, 0);
LABEL_25:
    *(_QWORD *)(v10 + 448) = *v11;
    v12 = v11[1];
    if ( v12 )
      HMUnlockObject(v12);
  }
  return v3;
}

```

## disassembly

```asm
0x14002b230  mov     [rsp+arg_8], rbx
0x14002b235  push    rsi
0x14002b236  sub     rsp, 40h
0x14002b23a  mov     rsi, rdx
0x14002b23d  mov     rbx, rcx
0x14002b240  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002b247  nop     dword ptr [rax+rax+00h]
0x14002b24c  test    rax, rax
0x14002b24f  jz      loc_14002B57A
0x14002b255  mov     rcx, [rax]
0x14002b258  mov     rax, [rcx+1C0h]
0x14002b25f  mov     [rsp+48h+BugCheckParameter3], rax
0x14002b264  lea     rax, [rsp+48h+BugCheckParameter3]
0x14002b269  mov     [rcx+1C0h], rax
0x14002b270  mov     [rsp+48h+var_10], rbx
0x14002b275  test    rbx, rbx
0x14002b278  jz      short loc_14002B289
0x14002b27a  mov     rcx, rbx
0x14002b27d  call    cs:__imp_HMLockObject
0x14002b284  nop     dword ptr [rax+rax+00h]
0x14002b289  mov     [rsp+48h+arg_0], rdi
0x14002b28e  xchg    ax, ax
0x14002b290  test    rbx, rbx
0x14002b293  jz      loc_14002B3A1
0x14002b299  cmp     [rbx+10h], rsi
0x14002b29d  jz      short loc_14002B2E4
0x14002b29f  mov     rcx, [rbx+70h]; struct tagWND *
0x14002b2a3  test    rcx, rcx
0x14002b2a6  jnz     loc_14002B401
0x14002b2ac  mov     rbx, [rbx+58h]
0x14002b2b0  mov     rdi, [rsp+48h+var_10]
0x14002b2b5  mov     [rsp+48h+var_10], rbx
0x14002b2ba  test    rbx, rbx
0x14002b2bd  jz      short loc_14002B2CE
0x14002b2bf  mov     rcx, rbx
0x14002b2c2  call    cs:__imp_HMLockObject
0x14002b2c9  nop     dword ptr [rax+rax+00h]
0x14002b2ce  test    rdi, rdi
0x14002b2d1  jz      short loc_14002B290
0x14002b2d3  mov     rcx, rdi
0x14002b2d6  call    cs:__imp_HMUnlockObject
0x14002b2dd  nop     dword ptr [rax+rax+00h]
0x14002b2e2  jmp     short loc_14002B290
0x14002b2e4  mov     rcx, [rbx+28h]
0x14002b2e8  test    byte ptr [rcx+1Bh], 2
0x14002b2ec  jnz     loc_14002B50C
0x14002b2f2  cmp     qword ptr [rcx+88h], 0
0x14002b2fa  jnz     short loc_14002B302
0x14002b2fc  test    byte ptr [rcx+11h], 10h
0x14002b300  jz      short loc_14002B29F
0x14002b302  test    byte ptr [rcx+18h], 20h
0x14002b306  jz      loc_14002B476
0x14002b30c  mov     rbx, [rbx+58h]
0x14002b310  test    rbx, rbx
0x14002b313  jz      loc_14002B476
0x14002b319  cmp     [rbx+10h], rsi
0x14002b31d  jnz     short loc_14002B30C
0x14002b31f  mov     rcx, [rbx+28h]
0x14002b323  cmp     qword ptr [rcx+88h], 0
0x14002b32b  jnz     short loc_14002B333
0x14002b32d  test    byte ptr [rcx+11h], 10h
0x14002b331  jz      short loc_14002B30C
0x14002b333  test    byte ptr [rcx+18h], 20h
0x14002b337  jnz     short loc_14002B30C
0x14002b339  cmp     [rsp+48h+BugCheckParameter3], 0FFFFFFFFFFFFFFFFh
0x14002b33f  jz      short loc_14002B38D
0x14002b341  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002b348  nop     dword ptr [rax+rax+00h]
0x14002b34d  test    rax, rax
0x14002b350  jz      loc_14002B588
0x14002b356  mov     rdx, [rax]
0x14002b359  mov     rcx, [rdx+1C0h]
0x14002b360  lea     rax, [rsp+48h+BugCheckParameter3]
0x14002b365  cmp     rcx, rax
0x14002b368  jnz     loc_14002B52A
0x14002b36e  mov     rax, [rcx]
0x14002b371  mov     [rdx+1C0h], rax
0x14002b378  mov     rcx, [rcx+8]
0x14002b37c  test    rcx, rcx
0x14002b37f  jz      short loc_14002B38D
0x14002b381  call    cs:__imp_HMUnlockObject
0x14002b388  nop     dword ptr [rax+rax+00h]
0x14002b38d  mov     rax, rbx
0x14002b390  mov     rdi, [rsp+48h+arg_0]
0x14002b395  mov     rbx, [rsp+48h+arg_8]
0x14002b39a  add     rsp, 40h
0x14002b39e  pop     rsi
0x14002b39f  retn
0x14002b3a1  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002b3a8  nop     dword ptr [rax+rax+00h]
0x14002b3ad  test    rax, rax
0x14002b3b0  jz      loc_14002B581
0x14002b3b6  mov     rdx, [rax]
0x14002b3b9  mov     rcx, [rdx+1C0h]
0x14002b3c0  lea     rax, [rsp+48h+BugCheckParameter3]
0x14002b3c5  cmp     rcx, rax
0x14002b3c8  jnz     loc_14002B4E4
0x14002b3ce  mov     rax, [rcx]
0x14002b3d1  mov     [rdx+1C0h], rax
0x14002b3d8  mov     rax, [rcx+8]
0x14002b3dc  test    rax, rax
0x14002b3df  jz      short loc_14002B3F0
0x14002b3e1  mov     rcx, rax
0x14002b3e4  call    cs:__imp_HMUnlockObject
0x14002b3eb  nop     dword ptr [rax+rax+00h]
0x14002b3f0  mov     rdi, [rsp+48h+arg_0]
0x14002b3f5  mov     rbx, [rsp+48h+arg_8]
0x14002b3fa  add     rsp, 40h
0x14002b3fe  pop     rsi
0x14002b3ff  retn
0x14002b401  mov     rdx, rsi; struct tagTHREADINFO *
0x14002b404  call    ?xxxInternalDoPaint@@YAPEAUtagWND@@PEAU1@PEAUtagTHREADINFO@@@Z; xxxInternalDoPaint(tagWND *,tagTHREADINFO *)
0x14002b409  mov     rdi, rax
0x14002b40c  test    rax, rax
0x14002b40f  jz      loc_14002B2AC
0x14002b415  cmp     rax, rbx
0x14002b418  jz      loc_14002B59D
0x14002b41e  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002b425  nop     dword ptr [rax+rax+00h]
0x14002b42a  test    rax, rax
0x14002b42d  jz      loc_14002B58F
0x14002b433  mov     rdx, [rax]
0x14002b436  mov     rcx, [rdx+1C0h]
0x14002b43d  lea     rax, [rsp+48h+BugCheckParameter3]
0x14002b442  cmp     rcx, rax
0x14002b445  jnz     loc_14002B552
0x14002b44b  mov     rax, [rcx]
0x14002b44e  mov     [rdx+1C0h], rax
0x14002b455  mov     rcx, [rcx+8]
0x14002b459  test    rcx, rcx
0x14002b45c  jnz     loc_14002B5F2
0x14002b462  mov     rbx, [rsp+48h+arg_8]
0x14002b467  mov     rax, rdi
0x14002b46a  mov     rdi, [rsp+48h+arg_0]
0x14002b46f  add     rsp, 40h
0x14002b473  pop     rsi
0x14002b474  retn
0x14002b476  lea     rcx, [rsp+48h+BugCheckParameter3]; BugCheckParameter3
0x14002b47b  call    ??$ManualUnlock@X@?$Win32HMThreadLockBase@UtagCURSOR@@$00$00@@QEAAPEAUtagCURSOR@@XZ; Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>(void)
0x14002b480  cmp     [rsp+48h+BugCheckParameter3], 0FFFFFFFFFFFFFFFFh
0x14002b486  mov     rbx, rax
0x14002b489  jz      loc_14002B38D
0x14002b48f  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002b496  nop     dword ptr [rax+rax+00h]
0x14002b49b  test    rax, rax
0x14002b49e  jz      loc_14002B596
0x14002b4a4  mov     rdx, [rax]
0x14002b4a7  mov     rcx, [rdx+1C0h]
0x14002b4ae  lea     rax, [rsp+48h+BugCheckParameter3]
0x14002b4b3  cmp     rcx, rax
0x14002b4b6  jz      loc_14002B36E
0x14002b4bc  mov     r8, rdx; BugCheckParameter2
0x14002b4bf  mov     [rsp+48h+BugCheckParameter4], 0; BugCheckParameter4
0x14002b4c8  mov     edx, 3Bh ; ';'; BugCheckParameter1
0x14002b4cd  lea     r9, [rsp+48h+BugCheckParameter3]; BugCheckParameter3
0x14002b4d2  mov     ecx, 164h; BugCheckCode
0x14002b4d7  call    cs:__imp_KeBugCheckEx
0x14002b4e4  mov     r8, rdx; BugCheckParameter2
0x14002b4e7  mov     [rsp+48h+BugCheckParameter4], 0; BugCheckParameter4
0x14002b4f0  mov     edx, 3Bh ; ';'; BugCheckParameter1
0x14002b4f5  lea     r9, [rsp+48h+BugCheckParameter3]; BugCheckParameter3
0x14002b4fa  mov     ecx, 164h; BugCheckCode
0x14002b4ff  call    cs:__imp_KeBugCheckEx
0x14002b50c  mov     rcx, rbx
0x14002b50f  call    xxxCompositedPaint
0x14002b514  mov     rbx, [rbx+58h]
0x14002b518  lea     rdx, [rsp+48h+BugCheckParameter3]
0x14002b51d  mov     rcx, rbx
0x14002b520  call    ??$Win32HM_ExchangeThreadLock@$00@@YAPEAU_HEAD@@PEAU0@PEAU_Win32HMThreadLockItem@@@Z; Win32HM_ExchangeThreadLock<1>(_HEAD *,_Win32HMThreadLockItem *)
0x14002b525  jmp     loc_14002B290
0x14002b52a  mov     r8, rdx; BugCheckParameter2
0x14002b52d  mov     [rsp+48h+BugCheckParameter4], 0; BugCheckParameter4
0x14002b536  mov     edx, 3Bh ; ';'; BugCheckParameter1
0x14002b53b  lea     r9, [rsp+48h+BugCheckParameter3]; BugCheckParameter3
0x14002b540  mov     ecx, 164h; BugCheckCode
0x14002b545  call    cs:__imp_KeBugCheckEx
0x14002b552  mov     r8, rdx; BugCheckParameter2
0x14002b555  mov     [rsp+48h+BugCheckParameter4], 0; BugCheckParameter4
0x14002b55e  mov     edx, 3Bh ; ';'; BugCheckParameter1
0x14002b563  lea     r9, [rsp+48h+BugCheckParameter3]; BugCheckParameter3
0x14002b568  mov     ecx, 164h; BugCheckCode
0x14002b56d  call    cs:__imp_KeBugCheckEx
0x14002b57a  xor     ecx, ecx
0x14002b57c  jmp     loc_14002B258
0x14002b581  xor     edx, edx
0x14002b583  jmp     loc_14002B3B9
0x14002b588  xor     edx, edx
0x14002b58a  jmp     loc_14002B359
0x14002b58f  xor     edx, edx
0x14002b591  jmp     loc_14002B436
0x14002b596  xor     edx, edx
0x14002b598  jmp     loc_14002B4A7
0x14002b59d  lea     rcx, [rsp+48h+BugCheckParameter3]; BugCheckParameter3
0x14002b5a2  call    ??$ManualUnlock@X@?$Win32HMThreadLockBase@UtagCURSOR@@$00$00@@QEAAPEAUtagCURSOR@@XZ; Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>(void)
0x14002b5a7  cmp     [rsp+48h+BugCheckParameter3], 0FFFFFFFFFFFFFFFFh
0x14002b5ad  mov     rdi, rax
0x14002b5b0  jz      loc_14002B462
0x14002b5b6  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002b5bd  nop     dword ptr [rax+rax+00h]
0x14002b5c2  test    rax, rax
0x14002b5c5  jz      short loc_14002B62B
0x14002b5c7  mov     rdx, [rax]
0x14002b5ca  mov     rcx, [rdx+1C0h]
0x14002b5d1  lea     rax, [rsp+48h+BugCheckParameter3]
0x14002b5d6  cmp     rcx, rax
0x14002b5d9  jnz     short loc_14002B603
0x14002b5db  mov     rax, [rcx]
0x14002b5de  mov     [rdx+1C0h], rax
0x14002b5e5  mov     rcx, [rcx+8]
0x14002b5e9  test    rcx, rcx
0x14002b5ec  jz      loc_14002B462
0x14002b5f2  call    cs:__imp_HMUnlockObject
0x14002b5f9  nop     dword ptr [rax+rax+00h]
0x14002b5fe  jmp     loc_14002B462
0x14002b603  mov     r8, rdx; BugCheckParameter2
0x14002b606  mov     [rsp+48h+BugCheckParameter4], 0; BugCheckParameter4
0x14002b60f  mov     edx, 3Bh ; ';'; BugCheckParameter1
0x14002b614  lea     r9, [rsp+48h+BugCheckParameter3]; BugCheckParameter3
0x14002b619  mov     ecx, 164h; BugCheckCode
0x14002b61e  call    cs:__imp_KeBugCheckEx
0x14002b62b  xor     edx, edx
0x14002b62d  jmp     short loc_14002B5CA
```
