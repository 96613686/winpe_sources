# xxxInternalDoPaint(tagWND *,tagTHREADINFO *)

- ea: `0x140026160`
- end: `0x14002655f`
- name: `?xxxInternalDoPaint@@YAPEAUtagWND@@PEAU1@PEAUtagTHREADINFO@@@Z`
- size: `1023`
- prototype: `struct tagWND *__fastcall(struct tagWND *, struct tagTHREADINFO *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140025c10`
- `0x140026160`

## callees

- `0x14001c384`
- `0x140026160`
- `0x140026568`
- `0x140026840`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140026407`
- `ntoskrnl!KeBugCheckEx` at `0x14002642f`
- `ntoskrnl!KeBugCheckEx` at `0x140026475`
- `ntoskrnl!KeBugCheckEx` at `0x14002649d`
- `ntoskrnl!KeBugCheckEx` at `0x14002654e`
- `ntoskrnl!KeBugCheckEx` at `0x140026407`
- `ntoskrnl!KeBugCheckEx` at `0x14002642f`
- `ntoskrnl!KeBugCheckEx` at `0x140026475`
- `ntoskrnl!KeBugCheckEx` at `0x14002649d`
- `ntoskrnl!KeBugCheckEx` at `0x14002654e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140026170`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140026271`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400262d1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002634e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400263bf`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400264e6`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140026170`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140026271`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400262d1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002634e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400263bf`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400264e6`
- `win32kbase!HMLockObject` at `0x1400261ad`
- `win32kbase!HMLockObject` at `0x1400261f2`
- `win32kbase!HMLockObject` at `0x1400261ad`
- `win32kbase!HMLockObject` at `0x1400261f2`
- `win32kbase!HMUnlockObject` at `0x140026206`
- `win32kbase!HMUnlockObject` at `0x1400262b1`
- `win32kbase!HMUnlockObject` at `0x140026314`
- `win32kbase!HMUnlockObject` at `0x140026522`
- `win32kbase!HMUnlockObject` at `0x140026206`
- `win32kbase!HMUnlockObject` at `0x1400262b1`
- `win32kbase!HMUnlockObject` at `0x140026314`
- `win32kbase!HMUnlockObject` at `0x140026522`

## pseudocode

```c
struct tagWND *__fastcall xxxInternalDoPaint(struct tagWND *a1, struct tagTHREADINFO *a2)
{
  struct tagWND *v3; // rbx
  ULONG_PTR **CurrentThreadWin32Thread; // rax
  __int64 v5; // rdx
  ULONG_PTR *v6; // rcx
  struct tagWND *v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rcx
  ULONG_PTR *v10; // rax
  ULONG_PTR v11; // rdx
  ULONG_PTR *v12; // rcx
  ULONG_PTR v13; // rcx
  struct tagWND *result; // rax
  ULONG_PTR *v15; // rax
  ULONG_PTR v16; // rdx
  ULONG_PTR *v17; // rcx
  struct tagWND *v18; // rax
  __int64 v19; // rdi
  ULONG_PTR *v20; // rax
  ULONG_PTR v21; // rdx
  ULONG_PTR *v22; // rcx
  ULONG_PTR v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  ULONG_PTR *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  ULONG_PTR *v29; // rax
  ULONG_PTR v30; // rdx
  ULONG_PTR *v31; // rcx
  ULONG_PTR BugCheckParameter3; // [rsp+30h] [rbp-18h] BYREF
  struct tagWND *v33; // [rsp+38h] [rbp-10h]

  v3 = a1;
  CurrentThreadWin32Thread = (ULONG_PTR **)PsGetCurrentThreadWin32Thread(a1, a2);
  if ( CurrentThreadWin32Thread )
    v6 = *CurrentThreadWin32Thread;
  else
    v6 = 0;
  BugCheckParameter3 = v6[56];
  v6[56] = (ULONG_PTR)&BugCheckParameter3;
  v33 = v3;
  if ( v3 )
    HMLockObject(v3);
  while ( 1 )
  {
    while ( 1 )
    {
      if ( !v3 )
      {
        v15 = (ULONG_PTR *)PsGetCurrentThreadWin32Thread(v6, v5);
        if ( v15 )
          v16 = *v15;
        else
          v16 = 0;
        v17 = *(ULONG_PTR **)(v16 + 448);
        if ( v17 != &BugCheckParameter3 )
          KeBugCheckEx(0x164u, 0x3Bu, v16, (ULONG_PTR)&BugCheckParameter3, 0);
        *(_QWORD *)(v16 + 448) = *v17;
        result = (struct tagWND *)v17[1];
        if ( result )
          return (struct tagWND *)HMUnlockObject(v17[1]);
        return result;
      }
      if ( *((struct tagTHREADINFO **)v3 + 2) == a2 )
        break;
LABEL_7:
      v6 = (ULONG_PTR *)*((_QWORD *)v3 + 14);
      if ( v6 )
      {
        v18 = xxxInternalDoPaint((struct tagWND *)v6, a2);
        v19 = (__int64)v18;
        if ( v18 )
        {
          if ( v18 == v3 )
          {
            v19 = Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)&BugCheckParameter3);
            if ( BugCheckParameter3 == -1 )
              return (struct tagWND *)v19;
            v29 = (ULONG_PTR *)PsGetCurrentThreadWin32Thread(v28, v27);
            if ( v29 )
              v30 = *v29;
            else
              v30 = 0;
            v31 = *(ULONG_PTR **)(v30 + 448);
            if ( v31 != &BugCheckParameter3 )
              KeBugCheckEx(0x164u, 0x3Bu, v30, (ULONG_PTR)&BugCheckParameter3, 0);
            *(_QWORD *)(v30 + 448) = *v31;
            v23 = v31[1];
            if ( !v23 )
              return (struct tagWND *)v19;
          }
          else
          {
            v20 = (ULONG_PTR *)PsGetCurrentThreadWin32Thread(v6, v5);
            if ( v20 )
              v21 = *v20;
            else
              v21 = 0;
            v22 = *(ULONG_PTR **)(v21 + 448);
            if ( v22 != &BugCheckParameter3 )
              KeBugCheckEx(0x164u, 0x3Bu, v21, (ULONG_PTR)&BugCheckParameter3, 0);
            *(_QWORD *)(v21 + 448) = *v22;
            v23 = v22[1];
            if ( !v23 )
              return (struct tagWND *)v19;
          }
          HMUnlockObject(v23);
          return (struct tagWND *)v19;
        }
      }
      v3 = (struct tagWND *)*((_QWORD *)v3 + 11);
      v7 = v33;
      v33 = v3;
      if ( v3 )
        HMLockObject(v3);
      if ( v7 )
        HMUnlockObject(v7);
    }
    v8 = *((_QWORD *)v3 + 5);
    if ( (*(_BYTE *)(v8 + 27) & 2) == 0 )
      break;
    xxxCompositedPaint(v3);
    v3 = (struct tagWND *)*((_QWORD *)v3 + 11);
    Win32HM_ExchangeThreadLock<1>(v3, &BugCheckParameter3);
  }
  if ( !*(_QWORD *)(v8 + 136) && (*(_BYTE *)(v8 + 17) & 0x10) == 0 )
    goto LABEL_7;
  if ( (*(_BYTE *)(v8 + 24) & 0x20) != 0 )
  {
    while ( 1 )
    {
      v3 = (struct tagWND *)*((_QWORD *)v3 + 11);
      if ( !v3 )
        break;
      if ( *((struct tagTHREADINFO **)v3 + 2) == a2 )
      {
        v9 = *((_QWORD *)v3 + 5);
        if ( (*(_QWORD *)(v9 + 136) || (*(_BYTE *)(v9 + 17) & 0x10) != 0) && (*(_BYTE *)(v9 + 24) & 0x20) == 0 )
        {
          if ( BugCheckParameter3 == -1 )
            return v3;
          v10 = (ULONG_PTR *)PsGetCurrentThreadWin32Thread(v9, v5);
          if ( v10 )
            v11 = *v10;
          else
            v11 = 0;
          v12 = *(ULONG_PTR **)(v11 + 448);
          if ( v12 != &BugCheckParameter3 )
            KeBugCheckEx(0x164u, 0x3Bu, v11, (ULONG_PTR)&BugCheckParameter3, 0);
          goto LABEL_25;
        }
      }
    }
  }
  v3 = (struct tagWND *)Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)&BugCheckParameter3);
  if ( BugCheckParameter3 != -1 )
  {
    v26 = (ULONG_PTR *)PsGetCurrentThreadWin32Thread(v25, v24);
    if ( v26 )
      v11 = *v26;
    else
      v11 = 0;
    v12 = *(ULONG_PTR **)(v11 + 448);
    if ( v12 != &BugCheckParameter3 )
      KeBugCheckEx(0x164u, 0x3Bu, v11, (ULONG_PTR)&BugCheckParameter3, 0);
LABEL_25:
    *(_QWORD *)(v11 + 448) = *v12;
    v13 = v12[1];
    if ( v13 )
      HMUnlockObject(v13);
  }
  return v3;
}

```

## disassembly

```asm
0x140026160  mov     [rsp+arg_8], rbx
0x140026165  push    rsi
0x140026166  sub     rsp, 40h
0x14002616a  mov     rsi, rdx
0x14002616d  mov     rbx, rcx
0x140026170  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140026177  nop     dword ptr [rax+rax+00h]
0x14002617c  test    rax, rax
0x14002617f  jz      loc_1400264AA
0x140026185  mov     rcx, [rax]
0x140026188  mov     rax, [rcx+1C0h]
0x14002618f  mov     [rsp+48h+BugCheckParameter3], rax
0x140026194  lea     rax, [rsp+48h+BugCheckParameter3]
0x140026199  mov     [rcx+1C0h], rax
0x1400261a0  mov     [rsp+48h+var_10], rbx
0x1400261a5  test    rbx, rbx
0x1400261a8  jz      short loc_1400261B9
0x1400261aa  mov     rcx, rbx
0x1400261ad  call    cs:__imp_HMLockObject
0x1400261b4  nop     dword ptr [rax+rax+00h]
0x1400261b9  mov     [rsp+48h+arg_0], rdi
0x1400261be  xchg    ax, ax
0x1400261c0  test    rbx, rbx
0x1400261c3  jz      loc_1400262D1
0x1400261c9  cmp     [rbx+10h], rsi
0x1400261cd  jz      short loc_140026214
0x1400261cf  mov     rcx, [rbx+70h]; struct tagWND *
0x1400261d3  test    rcx, rcx
0x1400261d6  jnz     loc_140026331
0x1400261dc  mov     rbx, [rbx+58h]
0x1400261e0  mov     rdi, [rsp+48h+var_10]
0x1400261e5  mov     [rsp+48h+var_10], rbx
0x1400261ea  test    rbx, rbx
0x1400261ed  jz      short loc_1400261FE
0x1400261ef  mov     rcx, rbx
0x1400261f2  call    cs:__imp_HMLockObject
0x1400261f9  nop     dword ptr [rax+rax+00h]
0x1400261fe  test    rdi, rdi
0x140026201  jz      short loc_1400261C0
0x140026203  mov     rcx, rdi
0x140026206  call    cs:__imp_HMUnlockObject
0x14002620d  nop     dword ptr [rax+rax+00h]
0x140026212  jmp     short loc_1400261C0
0x140026214  mov     rcx, [rbx+28h]
0x140026218  test    byte ptr [rcx+1Bh], 2
0x14002621c  jnz     loc_14002643C
0x140026222  cmp     qword ptr [rcx+88h], 0
0x14002622a  jnz     short loc_140026232
0x14002622c  test    byte ptr [rcx+11h], 10h
0x140026230  jz      short loc_1400261CF
0x140026232  test    byte ptr [rcx+18h], 20h
0x140026236  jz      loc_1400263A6
0x14002623c  mov     rbx, [rbx+58h]
0x140026240  test    rbx, rbx
0x140026243  jz      loc_1400263A6
0x140026249  cmp     [rbx+10h], rsi
0x14002624d  jnz     short loc_14002623C
0x14002624f  mov     rcx, [rbx+28h]
0x140026253  cmp     qword ptr [rcx+88h], 0
0x14002625b  jnz     short loc_140026263
0x14002625d  test    byte ptr [rcx+11h], 10h
0x140026261  jz      short loc_14002623C
0x140026263  test    byte ptr [rcx+18h], 20h
0x140026267  jnz     short loc_14002623C
0x140026269  cmp     [rsp+48h+BugCheckParameter3], 0FFFFFFFFFFFFFFFFh
0x14002626f  jz      short loc_1400262BD
0x140026271  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140026278  nop     dword ptr [rax+rax+00h]
0x14002627d  test    rax, rax
0x140026280  jz      loc_1400264B8
0x140026286  mov     rdx, [rax]
0x140026289  mov     rcx, [rdx+1C0h]
0x140026290  lea     rax, [rsp+48h+BugCheckParameter3]
0x140026295  cmp     rcx, rax
0x140026298  jnz     loc_14002645A
0x14002629e  mov     rax, [rcx]
0x1400262a1  mov     [rdx+1C0h], rax
0x1400262a8  mov     rcx, [rcx+8]
0x1400262ac  test    rcx, rcx
0x1400262af  jz      short loc_1400262BD
0x1400262b1  call    cs:__imp_HMUnlockObject
0x1400262b8  nop     dword ptr [rax+rax+00h]
0x1400262bd  mov     rax, rbx
0x1400262c0  mov     rdi, [rsp+48h+arg_0]
0x1400262c5  mov     rbx, [rsp+48h+arg_8]
0x1400262ca  add     rsp, 40h
0x1400262ce  pop     rsi
0x1400262cf  retn
0x1400262d1  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400262d8  nop     dword ptr [rax+rax+00h]
0x1400262dd  test    rax, rax
0x1400262e0  jz      loc_1400264B1
0x1400262e6  mov     rdx, [rax]
0x1400262e9  mov     rcx, [rdx+1C0h]
0x1400262f0  lea     rax, [rsp+48h+BugCheckParameter3]
0x1400262f5  cmp     rcx, rax
0x1400262f8  jnz     loc_140026414
0x1400262fe  mov     rax, [rcx]
0x140026301  mov     [rdx+1C0h], rax
0x140026308  mov     rax, [rcx+8]
0x14002630c  test    rax, rax
0x14002630f  jz      short loc_140026320
0x140026311  mov     rcx, rax
0x140026314  call    cs:__imp_HMUnlockObject
0x14002631b  nop     dword ptr [rax+rax+00h]
0x140026320  mov     rdi, [rsp+48h+arg_0]
0x140026325  mov     rbx, [rsp+48h+arg_8]
0x14002632a  add     rsp, 40h
0x14002632e  pop     rsi
0x14002632f  retn
0x140026331  mov     rdx, rsi; struct tagTHREADINFO *
0x140026334  call    ?xxxInternalDoPaint@@YAPEAUtagWND@@PEAU1@PEAUtagTHREADINFO@@@Z; xxxInternalDoPaint(tagWND *,tagTHREADINFO *)
0x140026339  mov     rdi, rax
0x14002633c  test    rax, rax
0x14002633f  jz      loc_1400261DC
0x140026345  cmp     rax, rbx
0x140026348  jz      loc_1400264CD
0x14002634e  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140026355  nop     dword ptr [rax+rax+00h]
0x14002635a  test    rax, rax
0x14002635d  jz      loc_1400264BF
0x140026363  mov     rdx, [rax]
0x140026366  mov     rcx, [rdx+1C0h]
0x14002636d  lea     rax, [rsp+48h+BugCheckParameter3]
0x140026372  cmp     rcx, rax
0x140026375  jnz     loc_140026482
0x14002637b  mov     rax, [rcx]
0x14002637e  mov     [rdx+1C0h], rax
0x140026385  mov     rcx, [rcx+8]
0x140026389  test    rcx, rcx
0x14002638c  jnz     loc_140026522
0x140026392  mov     rbx, [rsp+48h+arg_8]
0x140026397  mov     rax, rdi
0x14002639a  mov     rdi, [rsp+48h+arg_0]
0x14002639f  add     rsp, 40h
0x1400263a3  pop     rsi
0x1400263a4  retn
0x1400263a6  lea     rcx, [rsp+48h+BugCheckParameter3]; BugCheckParameter3
0x1400263ab  call    ??$ManualUnlock@X@?$Win32HMThreadLockBase@UtagCURSOR@@$00$00@@QEAAPEAUtagCURSOR@@XZ; Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>(void)
0x1400263b0  cmp     [rsp+48h+BugCheckParameter3], 0FFFFFFFFFFFFFFFFh
0x1400263b6  mov     rbx, rax
0x1400263b9  jz      loc_1400262BD
0x1400263bf  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400263c6  nop     dword ptr [rax+rax+00h]
0x1400263cb  test    rax, rax
0x1400263ce  jz      loc_1400264C6
0x1400263d4  mov     rdx, [rax]
0x1400263d7  mov     rcx, [rdx+1C0h]
0x1400263de  lea     rax, [rsp+48h+BugCheckParameter3]
0x1400263e3  cmp     rcx, rax
0x1400263e6  jz      loc_14002629E
0x1400263ec  mov     r8, rdx; BugCheckParameter2
0x1400263ef  mov     [rsp+48h+BugCheckParameter4], 0; BugCheckParameter4
0x1400263f8  mov     edx, 3Bh ; ';'; BugCheckParameter1
0x1400263fd  lea     r9, [rsp+48h+BugCheckParameter3]; BugCheckParameter3
0x140026402  mov     ecx, 164h; BugCheckCode
0x140026407  call    cs:__imp_KeBugCheckEx
0x140026414  mov     r8, rdx; BugCheckParameter2
0x140026417  mov     [rsp+48h+BugCheckParameter4], 0; BugCheckParameter4
0x140026420  mov     edx, 3Bh ; ';'; BugCheckParameter1
0x140026425  lea     r9, [rsp+48h+BugCheckParameter3]; BugCheckParameter3
0x14002642a  mov     ecx, 164h; BugCheckCode
0x14002642f  call    cs:__imp_KeBugCheckEx
0x14002643c  mov     rcx, rbx
0x14002643f  call    xxxCompositedPaint
0x140026444  mov     rbx, [rbx+58h]
0x140026448  lea     rdx, [rsp+48h+BugCheckParameter3]
0x14002644d  mov     rcx, rbx
0x140026450  call    ??$Win32HM_ExchangeThreadLock@$00@@YAPEAU_HEAD@@PEAU0@PEAU_Win32HMThreadLockItem@@@Z; Win32HM_ExchangeThreadLock<1>(_HEAD *,_Win32HMThreadLockItem *)
0x140026455  jmp     loc_1400261C0
0x14002645a  mov     r8, rdx; BugCheckParameter2
0x14002645d  mov     [rsp+48h+BugCheckParameter4], 0; BugCheckParameter4
0x140026466  mov     edx, 3Bh ; ';'; BugCheckParameter1
0x14002646b  lea     r9, [rsp+48h+BugCheckParameter3]; BugCheckParameter3
0x140026470  mov     ecx, 164h; BugCheckCode
0x140026475  call    cs:__imp_KeBugCheckEx
0x140026482  mov     r8, rdx; BugCheckParameter2
0x140026485  mov     [rsp+48h+BugCheckParameter4], 0; BugCheckParameter4
0x14002648e  mov     edx, 3Bh ; ';'; BugCheckParameter1
0x140026493  lea     r9, [rsp+48h+BugCheckParameter3]; BugCheckParameter3
0x140026498  mov     ecx, 164h; BugCheckCode
0x14002649d  call    cs:__imp_KeBugCheckEx
0x1400264aa  xor     ecx, ecx
0x1400264ac  jmp     loc_140026188
0x1400264b1  xor     edx, edx
0x1400264b3  jmp     loc_1400262E9
0x1400264b8  xor     edx, edx
0x1400264ba  jmp     loc_140026289
0x1400264bf  xor     edx, edx
0x1400264c1  jmp     loc_140026366
0x1400264c6  xor     edx, edx
0x1400264c8  jmp     loc_1400263D7
0x1400264cd  lea     rcx, [rsp+48h+BugCheckParameter3]; BugCheckParameter3
0x1400264d2  call    ??$ManualUnlock@X@?$Win32HMThreadLockBase@UtagCURSOR@@$00$00@@QEAAPEAUtagCURSOR@@XZ; Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>(void)
0x1400264d7  cmp     [rsp+48h+BugCheckParameter3], 0FFFFFFFFFFFFFFFFh
0x1400264dd  mov     rdi, rax
0x1400264e0  jz      loc_140026392
0x1400264e6  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400264ed  nop     dword ptr [rax+rax+00h]
0x1400264f2  test    rax, rax
0x1400264f5  jz      short loc_14002655B
0x1400264f7  mov     rdx, [rax]
0x1400264fa  mov     rcx, [rdx+1C0h]
0x140026501  lea     rax, [rsp+48h+BugCheckParameter3]
0x140026506  cmp     rcx, rax
0x140026509  jnz     short loc_140026533
0x14002650b  mov     rax, [rcx]
0x14002650e  mov     [rdx+1C0h], rax
0x140026515  mov     rcx, [rcx+8]
0x140026519  test    rcx, rcx
0x14002651c  jz      loc_140026392
0x140026522  call    cs:__imp_HMUnlockObject
0x140026529  nop     dword ptr [rax+rax+00h]
0x14002652e  jmp     loc_140026392
0x140026533  mov     r8, rdx; BugCheckParameter2
0x140026536  mov     [rsp+48h+BugCheckParameter4], 0; BugCheckParameter4
0x14002653f  mov     edx, 3Bh ; ';'; BugCheckParameter1
0x140026544  lea     r9, [rsp+48h+BugCheckParameter3]; BugCheckParameter3
0x140026549  mov     ecx, 164h; BugCheckCode
0x14002654e  call    cs:__imp_KeBugCheckEx
0x14002655b  xor     edx, edx
0x14002655d  jmp     short loc_1400264FA
```
