# SkiSelectThread

- ea: `0x140099078`
- end: `0x140099332`
- name: `SkiSelectThread`
- size: `698`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1400ee8b0`

## callees

- `0x140094078`
- `0x140098e54`
- `0x140098f00`
- `0x140099078`
- `0x14009a540`
- `0x1400f0eb0`

## pseudocode

```c
__int64 __fastcall SkiSelectThread(unsigned int a1, char a2, unsigned __int8 a3, __int64 a4, unsigned __int64 a5)
{
  __int64 v8; // rsi
  struct _EXCEPTION_REGISTRATION_RECORD *ExceptionList; // rdi
  ULONG_PTR Handler; // rbx
  char v11; // r15
  int v12; // ecx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // r8
  unsigned __int8 v16; // cl
  unsigned __int8 v17; // dl
  _DWORD *v19; // rax
  struct _EXCEPTION_REGISTRATION_RECORD *v20; // rax
  int v21; // [rsp+20h] [rbp-48h]
  ULONG_PTR BugCheckParameter3[8]; // [rsp+28h] [rbp-40h] BYREF

  v8 = a1;
  v21 = 0;
  _InterlockedIncrement(&SkiUnrestrictedThreadCount);
  ExceptionList = KeGetPcr()->NtTib.ExceptionList;
  Handler = (ULONG_PTR)ExceptionList->Handler;
  BugCheckParameter3[0] = Handler;
  if ( SkiUnrestrictedThreadCount < 0 )
  {
    if ( a3 >= 2u && a2 == 2 )
    {
      Handler = (ULONG_PTR)ExceptionList[2].Handler;
LABEL_15:
      _InterlockedAdd(&SkiUnrestrictedThreadCount, 0xFFFFFFFF);
      v11 = 0;
      goto LABEL_29;
    }
    goto LABEL_20;
  }
  v11 = 1;
  if ( a2 == 1 )
  {
    if ( !a3 && !Handler && qword_140167138 + (unsigned __int64)(a4 & 0xFFF) <= 0x1000 )
    {
      v12 = SkiSelectEnclaveThread(HIDWORD(a5), a1, BugCheckParameter3);
      if ( v12 >= 0 )
      {
        Handler = BugCheckParameter3[0];
        goto LABEL_29;
      }
LABEL_44:
      _InterlockedDecrement(&SkiUnrestrictedThreadCount);
      return (unsigned int)v12;
    }
LABEL_20:
    v12 = -1073741811;
    goto LABEL_44;
  }
  if ( Handler )
  {
    if ( a3 >= 2u && (!a1 || a1 == *(_DWORD *)(Handler + 168)) )
      goto LABEL_15;
    goto LABEL_20;
  }
  if ( a1 )
  {
    v13 = SkiLockThreadEntry(a1, 0, 0);
    Handler = v13;
    if ( !v13 )
      goto LABEL_20;
    if ( _interlockedbittestandset((volatile signed __int32 *)(v13 + 172), 4u) )
    {
      _InterlockedDecrement((volatile signed __int32 *)(SkiThreadTable + 8 * v8));
      goto LABEL_20;
    }
    _InterlockedDecrement((volatile signed __int32 *)(SkiThreadTable + 8 * v8));
    v21 = 16;
  }
  else
  {
    if ( !a2 )
      goto LABEL_20;
    if ( a3 < 2u )
    {
      if ( _InterlockedDecrement(&SkiThreadPoolCount) < 0 )
      {
        _InterlockedIncrement(&SkiThreadPoolCount);
        goto LABEL_20;
      }
      do
        _BitScanForward((unsigned int *)&v14, SkiThreadPoolMask);
      while ( !_interlockedbittestandreset(&SkiThreadPoolMask, v14) );
      Handler = *(_QWORD *)(SkiThreadTable + 8 * v14);
    }
    else
    {
      Handler = (ULONG_PTR)ExceptionList[2].Handler;
    }
  }
LABEL_29:
  v15 = *(_QWORD *)(Handler + 128);
  v16 = 3;
  if ( a3 <= 2u )
    v16 = a3;
  v17 = *(_BYTE *)(v15 + 298);
  if ( v16 < v17 )
    goto LABEL_40;
  if ( (*(_DWORD *)(v15 + 208) & 0x200) != 0 )
    goto LABEL_38;
  if ( a2 )
  {
    if ( v16 != v17 || v16 >= 3u )
      goto LABEL_38;
LABEL_40:
    v12 = -1073741811;
    _InterlockedAnd((volatile signed __int32 *)(Handler + 172), ~v21);
    if ( *(_BYTE *)(v15 + 296) )
    {
      if ( *(_DWORD *)(Handler + 168) )
      {
        *(_QWORD *)(Handler + 136) = 0;
        _interlockedbittestandset(&SkiThreadPoolMask, *(_DWORD *)(Handler + 168));
        _InterlockedIncrement(&SkiThreadPoolCount);
      }
    }
    if ( !v11 )
      return (unsigned int)v12;
    goto LABEL_44;
  }
  if ( v16 != v17 )
    goto LABEL_40;
LABEL_38:
  if ( *(_QWORD *)(Handler + 144) )
  {
    if ( *(_QWORD *)(Handler + 136) != a4 )
      goto LABEL_40;
  }
  else if ( *(_DWORD *)(Handler + 168) )
  {
    *(_QWORD *)(Handler + 136) = a4;
  }
  if ( SkiUnrestrictedThreadCount >= 0 )
  {
    BYTE5(ExceptionList[11].Handler) = a3;
    __writecr8(v16);
  }
  else
  {
    HIBYTE(ExceptionList[11].Handler) = 1;
  }
  *(_QWORD *)(Handler + 64) = ExceptionList;
  ExceptionList->Handler = (PEXCEPTION_ROUTINE)Handler;
  ExceptionList[159].Handler = (PEXCEPTION_ROUTINE)Handler;
  v19 = *(_DWORD **)(Handler + 40);
  if ( v19 && (*v19 & DWORD2(xmmword_140167170)) != 0 )
    _InterlockedOr((volatile signed __int32 *)(Handler + 172), 2u);
  v20 = *(struct _EXCEPTION_REGISTRATION_RECORD **)(Handler + 80);
  if ( v20 && v20 != ExceptionList[4].Next && (*(_DWORD *)(Handler + 172) & 0x40) == 0 )
  {
    SkiUpdateSpeculationControl();
    SkeSelectProcessAddressSpace(*(_QWORD *)(Handler + 80));
  }
  SkiUpdateXStateForVtlTransition(Handler);
  return 0;
}

```

## disassembly

```asm
0x140099078  push    rbx
0x14009907a  push    rbp
0x14009907b  push    rsi
0x14009907c  push    rdi
0x14009907d  push    r12
0x14009907f  push    r14
0x140099081  push    r15
0x140099083  sub     rsp, 30h
0x140099087  mov     r12, r9
0x14009908a  movzx   ebp, r8b
0x14009908e  mov     r14b, dl
0x140099091  mov     esi, ecx
0x140099093  mov     [rsp+68h+var_48], 0
0x14009909b  lock inc cs:SkiUnrestrictedThreadCount
0x1400990a2  mov     rdi, gs:0
0x1400990ab  or      ecx, 0FFFFFFFFh
0x1400990ae  mov     eax, cs:SkiUnrestrictedThreadCount
0x1400990b4  mov     rbx, [rdi+8]
0x1400990b8  mov     [rsp+68h+BugCheckParameter3], rbx
0x1400990bd  test    eax, eax
0x1400990bf  jns     short loc_1400990DA
0x1400990c1  cmp     bpl, 2
0x1400990c5  jb      loc_14009918F
0x1400990cb  cmp     dl, 2
0x1400990ce  jnz     loc_14009918F
0x1400990d4  mov     rbx, [rdi+28h]
0x1400990d8  jmp     short loc_140099152
0x1400990da  mov     r15b, 1
0x1400990dd  cmp     r14b, r15b
0x1400990e0  jnz     short loc_14009913B
0x1400990e2  test    r8b, r8b
0x1400990e5  jnz     loc_14009918F
0x1400990eb  test    rbx, rbx
0x1400990ee  jnz     loc_14009918F
0x1400990f4  mov     eax, r12d
0x1400990f7  and     eax, 0FFFh
0x1400990fc  add     rax, cs:qword_140167138
0x140099103  cmp     rax, 1000h
0x140099109  ja      loc_14009918F
0x14009910f  mov     rcx, [rsp+68h+arg_20]
0x140099117  lea     r8, [rsp+68h+BugCheckParameter3]
0x14009911c  shr     rcx, 20h
0x140099120  mov     edx, esi
0x140099122  call    SkiSelectEnclaveThread
0x140099127  mov     ecx, eax
0x140099129  test    eax, eax
0x14009912b  js      loc_140099286
0x140099131  mov     rbx, [rsp+68h+BugCheckParameter3]
0x140099136  jmp     loc_1400991EA
0x14009913b  test    rbx, rbx
0x14009913e  jz      short loc_140099161
0x140099140  cmp     bpl, 2
0x140099144  jb      short loc_14009918F
0x140099146  test    esi, esi
0x140099148  jz      short loc_140099152
0x14009914a  cmp     esi, [rbx+0A8h]
0x140099150  jnz     short loc_14009918F
0x140099152  lock add cs:SkiUnrestrictedThreadCount, ecx
0x140099159  xor     r15b, r15b
0x14009915c  jmp     loc_1400991EA
0x140099161  test    esi, esi
0x140099163  jz      short loc_1400991A4
0x140099165  xor     r8d, r8d
0x140099168  xor     edx, edx
0x14009916a  mov     ecx, esi
0x14009916c  call    SkiLockThreadEntry
0x140099171  mov     rbx, rax
0x140099174  test    rax, rax
0x140099177  jz      short loc_14009918F
0x140099179  lock bts dword ptr [rax+0ACh], 4
0x140099182  mov     rax, cs:SkiThreadTable
0x140099189  jnb     short loc_140099199
0x14009918b  lock dec dword ptr [rax+rsi*8]
0x14009918f  mov     ecx, 0C000000Dh
0x140099194  jmp     loc_140099286
0x140099199  lock dec dword ptr [rax+rsi*8]
0x14009919d  or      [rsp+68h+var_48], 10h
0x1400991a2  jmp     short loc_1400991EA
0x1400991a4  test    r14b, r14b
0x1400991a7  jz      short loc_14009918F
0x1400991a9  cmp     bpl, 2
0x1400991ad  jb      short loc_1400991B5
0x1400991af  mov     rbx, [rdi+28h]
0x1400991b3  jmp     short loc_1400991EA
0x1400991b5  mov     eax, ecx
0x1400991b7  lock xadd cs:SkiThreadPoolCount, eax
0x1400991bf  add     eax, ecx
0x1400991c1  jns     short loc_1400991CC
0x1400991c3  lock inc cs:SkiThreadPoolCount
0x1400991ca  jmp     short loc_14009918F
0x1400991cc  mov     eax, cs:SkiThreadPoolMask
0x1400991d2  bsf     ecx, eax
0x1400991d5  lock btr cs:SkiThreadPoolMask, ecx
0x1400991dd  jnb     short loc_1400991CC
0x1400991df  mov     rax, cs:SkiThreadTable
0x1400991e6  mov     rbx, [rax+rcx*8]
0x1400991ea  mov     r8, [rbx+80h]
0x1400991f1  cmp     bpl, 2
0x1400991f5  mov     ecx, 3
0x1400991fa  cmovbe  ecx, ebp
0x1400991fd  mov     dl, [r8+12Ah]
0x140099204  cmp     cl, dl
0x140099206  jb      short loc_14009923C
0x140099208  test    dword ptr [r8+0D0h], 200h
0x140099213  jnz     short loc_140099229
0x140099215  test    r14b, r14b
0x140099218  jnz     short loc_140099220
0x14009921a  cmp     cl, dl
0x14009921c  jz      short loc_140099229
0x14009921e  jmp     short loc_14009923C
0x140099220  cmp     cl, dl
0x140099222  jnz     short loc_140099229
0x140099224  cmp     cl, 3
0x140099227  jb      short loc_14009923C
0x140099229  cmp     qword ptr [rbx+90h], 0
0x140099231  jz      short loc_140099294
0x140099233  cmp     [rbx+88h], r12
0x14009923a  jz      short loc_1400992A4
0x14009923c  mov     ecx, 0C000000Dh
0x140099241  mov     eax, [rsp+68h+var_48]
0x140099245  not     eax
0x140099247  lock and [rbx+0ACh], eax
0x14009924e  cmp     byte ptr [r8+128h], 0
0x140099256  jz      short loc_140099281
0x140099258  cmp     dword ptr [rbx+0A8h], 0
0x14009925f  jz      short loc_140099281
0x140099261  mov     qword ptr [rbx+88h], 0
0x14009926c  mov     eax, [rbx+0A8h]
0x140099272  lock bts cs:SkiThreadPoolMask, eax
0x14009927a  lock inc cs:SkiThreadPoolCount
0x140099281  test    r15b, r15b
0x140099284  jz      short loc_14009928D
0x140099286  lock dec cs:SkiUnrestrictedThreadCount
0x14009928d  mov     eax, ecx
0x14009928f  jmp     loc_140099322
0x140099294  cmp     dword ptr [rbx+0A8h], 0
0x14009929b  jz      short loc_1400992A4
0x14009929d  mov     [rbx+88h], r12
0x1400992a4  mov     eax, cs:SkiUnrestrictedThreadCount
0x1400992aa  test    eax, eax
0x1400992ac  jns     short loc_1400992B7
0x1400992ae  mov     byte ptr [rdi+0BFh], 1
0x1400992b5  jmp     short loc_1400992C5
0x1400992b7  mov     [rdi+0BDh], bpl
0x1400992be  movzx   eax, cl
0x1400992c1  mov     cr8, rax
0x1400992c5  mov     [rbx+40h], rdi
0x1400992c9  mov     [rdi+8], rbx
0x1400992cd  mov     [rdi+9F8h], rbx
0x1400992d4  mov     rax, [rbx+28h]
0x1400992d8  test    rax, rax
0x1400992db  jz      short loc_1400992EF
0x1400992dd  mov     eax, [rax]
0x1400992df  test    dword ptr cs:xmmword_140167170+8, eax
0x1400992e5  jz      short loc_1400992EF
0x1400992e7  lock or dword ptr [rbx+0ACh], 2
0x1400992ef  mov     rax, [rbx+50h]
0x1400992f3  test    rax, rax
0x1400992f6  jz      short loc_140099316
0x1400992f8  cmp     rax, [rdi+40h]
0x1400992fc  jz      short loc_140099316
0x1400992fe  mov     eax, [rbx+0ACh]
0x140099304  test    al, 40h
0x140099306  jnz     short loc_140099316
0x140099308  call    SkiUpdateSpeculationControl
0x14009930d  mov     rcx, [rbx+50h]
0x140099311  call    SkeSelectProcessAddressSpace
0x140099316  xor     edx, edx
0x140099318  mov     rcx, rbx; BugCheckParameter3
0x14009931b  call    SkiUpdateXStateForVtlTransition
0x140099320  xor     eax, eax
0x140099322  add     rsp, 30h
0x140099326  pop     r15
0x140099328  pop     r14
0x14009932a  pop     r12
0x14009932c  pop     rdi
0x14009932d  pop     rsi
0x14009932e  pop     rbp
0x14009932f  pop     rbx
0x140099330  retn
```
