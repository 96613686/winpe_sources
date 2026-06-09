# CreateAniIcon(ushort const *,ushort *,int,ulong *,int,HICON__ * *,ulong,ulong *,ulong)

- ea: `0x180001218`
- end: `0x1800013d6`
- name: `?CreateAniIcon@@YAPEAUHICON__@@PEBGPEAGHPEAKHPEAPEAU1@K2K@Z`
- size: `446`
- prototype: `HICON __fastcall(const unsigned __int16 *, unsigned __int16 *, int, unsigned int *, int, HICON *, unsigned int, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002368`

## callees

- `0x180001218`
- `0x180003b18`
- `0x180005f7c`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserDestroyCursor` at `0x180001392`
- `win32u!NtUserDestroyCursor` at `0x1800013cc`
- `win32u!NtUserDestroyCursor` at `0x180001392`
- `win32u!NtUserDestroyCursor` at `0x1800013cc`
- `win32u!NtUserCreateEmptyCursorObject` at `0x18000126f`
- `win32u!NtUserCreateEmptyCursorObject` at `0x18000126f`
- `ntdll!RtlFreeHeap` at `0x18000137c`
- `ntdll!RtlFreeHeap` at `0x18000137c`
- `ntdll!RtlAllocateHeap` at `0x1800012a6`
- `ntdll!RtlAllocateHeap` at `0x1800012a6`

## pseudocode

```c
HICON __fastcall CreateAniIcon(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        int a3,
        unsigned int *a4,
        int a5,
        HICON *a6,
        unsigned int a7,
        unsigned int *a8,
        unsigned int a9)
{
  __int64 v10; // rsi
  HICON EmptyCursorObject; // rbx
  int v13; // r15d
  char *Heap; // rax
  void *v15; // rdi
  char *v16; // r10
  __int64 v17; // rdx
  __int64 i; // rax
  unsigned int v19; // edx
  unsigned int v20; // edx
  int ThreadDefCursorSize; // eax
  _QWORD v23[2]; // [rsp+20h] [rbp-99h] BYREF
  __int16 v24; // [rsp+30h] [rbp-89h]
  int v25; // [rsp+38h] [rbp-81h]
  int v26; // [rsp+80h] [rbp-39h]
  int v27; // [rsp+84h] [rbp-35h]
  char *v28; // [rsp+88h] [rbp-31h]
  __int64 v29; // [rsp+90h] [rbp-29h]
  __int64 v30; // [rsp+98h] [rbp-21h]

  v10 = a3;
  memset_0(v23, 0, 0x88u);
  EmptyCursorObject = (HICON)NtUserCreateEmptyCursorObject((a9 >> 8) & 1);
  if ( !EmptyCursorObject )
    return 0;
  memset_0(v23, 0, 0x88u);
  v13 = 8;
  Heap = (char *)RtlAllocateHeap(pUserHeap, 8u, (unsigned int)(8 * (a5 + v10)));
  v15 = Heap;
  if ( !Heap )
  {
    NtUserDestroyCursor(EmptyCursorObject, 0);
    return 0;
  }
  v16 = &Heap[8 * a5];
  v28 = Heap;
  v29 = 8LL * a5 + 4 * v10;
  if ( (a9 & 0x40000) != 0 )
    v13 = 4104;
  v30 = 8LL * a5;
  v25 = v13;
  v17 = 0;
  v26 = a5;
  v27 = v10;
  v24 = 1;
  v23[1] = &szUSER32;
  for ( v23[0] = a1; (int)v17 < a5; v17 = (unsigned int)(v17 + 1) )
    *(_QWORD *)&Heap[8 * v17] = a6[v17];
  for ( i = 0; (int)i < (int)v10; i = (unsigned int)(i + 1) )
  {
    v19 = a7;
    if ( a8 )
      v19 = a8[i];
    *(_DWORD *)&v16[4 * i] = v19;
    v20 = i;
    if ( a4 )
      v20 = a4[i];
    *(_DWORD *)&v16[4 * v10 + 4 * i] = v20;
  }
  ThreadDefCursorSize = GetThreadDefCursorSize();
  if ( !(unsigned int)_SetCursorIconData(EmptyCursorObject, (struct tagCURSORDATA *)v23, ThreadDefCursorSize) )
  {
    NtUserDestroyCursor(EmptyCursorObject, 0);
    EmptyCursorObject = 0;
  }
  RtlFreeHeap(pUserHeap, 0, v15);
  return EmptyCursorObject;
}

```

## disassembly

```asm
0x180001218  mov     [rsp-8+arg_8], rbx
0x18000121d  push    rbp
0x18000121e  push    rsi
0x18000121f  push    rdi
0x180001220  push    r12
0x180001222  push    r13
0x180001224  push    r14
0x180001226  push    r15
0x180001228  lea     rbp, [rsp-7]
0x18000122d  sub     rsp, 0C0h
0x180001234  mov     rax, cs:__security_cookie
0x18000123b  xor     rax, rsp
0x18000123e  mov     [rbp+37h+var_40], rax
0x180001242  movsxd  r14, [rbp+37h+arg_20]
0x180001246  mov     r13, rcx
0x180001249  movsxd  rsi, r8d
0x18000124c  lea     rcx, [rsp+0F0h+var_D0]; void *
0x180001251  mov     edi, 88h
0x180001256  xor     edx, edx; Val
0x180001258  mov     r8d, edi; Size
0x18000125b  mov     r12, r9
0x18000125e  call    memset_0
0x180001263  mov     ecx, [rbp+37h+arg_40]
0x180001269  shr     ecx, 8
0x18000126c  and     ecx, 1
0x18000126f  call    cs:__imp_NtUserCreateEmptyCursorObject
0x180001275  mov     rbx, rax
0x180001278  test    rax, rax
0x18000127b  jz      loc_180001398
0x180001281  mov     r8d, edi; Size
0x180001284  lea     rcx, [rsp+0F0h+var_D0]; void *
0x180001289  xor     edx, edx; Val
0x18000128b  call    memset_0
0x180001290  mov     rcx, cs:pUserHeap; HeapHandle
0x180001297  lea     r8d, [r14+rsi]
0x18000129b  lea     r15d, [rdi-80h]
0x18000129f  shl     r8d, 3; Size
0x1800012a3  mov     edx, r15d; Flags
0x1800012a6  call    cs:__imp_RtlAllocateHeap
0x1800012ac  mov     rdi, rax
0x1800012af  test    rax, rax
0x1800012b2  jz      loc_18000138D
0x1800012b8  test    [rbp+37h+arg_40], 40000h
0x1800012c2  lea     rcx, ds:0[r14*8]
0x1800012ca  mov     r9, [rbp+37h+arg_28]
0x1800012ce  lea     r10, [rcx+rax]
0x1800012d2  mov     r8, [rbp+37h+arg_38]
0x1800012d6  lea     r11, [r10+rsi*4]
0x1800012da  mov     [rbp+37h+var_68], rax
0x1800012de  lea     rax, [rcx+rsi*4]
0x1800012e2  mov     [rbp+37h+var_60], rax
0x1800012e6  mov     eax, 1008h
0x1800012eb  cmovnz  r15d, eax
0x1800012ef  mov     [rbp+37h+var_58], rcx
0x1800012f3  mov     [rsp+0F0h+var_B8], r15d
0x1800012f8  lea     rax, ?szUSER32@@3PAGA; "USER32"
0x1800012ff  xor     edx, edx
0x180001301  mov     [rbp+37h+var_70], r14d
0x180001305  mov     [rbp+37h+var_6C], esi
0x180001308  mov     r15d, 1
0x18000130e  mov     [rsp+0F0h+var_C0], r15w
0x180001314  mov     [rsp+0F0h+var_C8], rax
0x180001319  mov     [rsp+0F0h+var_D0], r13
0x18000131e  test    r14d, r14d
0x180001321  jle     short loc_180001333
0x180001323  mov     rax, [r9+rdx*8]
0x180001327  mov     [rdi+rdx*8], rax
0x18000132b  add     edx, r15d
0x18000132e  cmp     edx, r14d
0x180001331  jl      short loc_180001323
0x180001333  xor     eax, eax
0x180001335  test    esi, esi
0x180001337  jle     short loc_180001357
0x180001339  mov     edx, [rbp+37h+arg_30]
0x18000133c  test    r8, r8
0x18000133f  jnz     short loc_180001387
0x180001341  mov     [r10+rax*4], edx
0x180001345  mov     edx, eax
0x180001347  test    r12, r12
0x18000134a  jnz     short loc_1800013C1
0x18000134c  mov     [r11+rax*4], edx
0x180001350  add     eax, r15d
0x180001353  cmp     eax, esi
0x180001355  jl      short loc_180001339
0x180001357  call    ?GetThreadDefCursorSize@@YAHXZ; GetThreadDefCursorSize(void)
0x18000135c  mov     r8d, eax; int
0x18000135f  lea     rdx, [rsp+0F0h+var_D0]; struct tagCURSORDATA *
0x180001364  mov     rcx, rbx; HICON
0x180001367  call    ?_SetCursorIconData@@YAHPEAUHICON__@@PEAUtagCURSORDATA@@H@Z; _SetCursorIconData(HICON__ *,tagCURSORDATA *,int)
0x18000136c  test    eax, eax
0x18000136e  jz      short loc_1800013C7
0x180001370  mov     rcx, cs:pUserHeap; HeapHandle
0x180001377  mov     r8, rdi; P
0x18000137a  xor     edx, edx; Flags
0x18000137c  call    cs:__imp_RtlFreeHeap
0x180001382  mov     rax, rbx
0x180001385  jmp     short loc_18000139A
0x180001387  mov     edx, [r8+rax*4]
0x18000138b  jmp     short loc_180001341
0x18000138d  xor     edx, edx
0x18000138f  mov     rcx, rbx
0x180001392  call    cs:__imp_NtUserDestroyCursor
0x180001398  xor     eax, eax
0x18000139a  mov     rcx, [rbp+37h+var_40]
0x18000139e  xor     rcx, rsp; StackCookie
0x1800013a1  call    __security_check_cookie
0x1800013a6  mov     rbx, [rsp+0F0h+arg_8]
0x1800013ae  add     rsp, 0C0h
0x1800013b5  pop     r15
0x1800013b7  pop     r14
0x1800013b9  pop     r13
0x1800013bb  pop     r12
0x1800013bd  pop     rdi
0x1800013be  pop     rsi
0x1800013bf  pop     rbp
0x1800013c0  retn
0x1800013c1  mov     edx, [r12+rax*4]
0x1800013c5  jmp     short loc_18000134C
0x1800013c7  xor     edx, edx
0x1800013c9  mov     rcx, rbx
0x1800013cc  call    cs:__imp_NtUserDestroyCursor
0x1800013d2  xor     ebx, ebx
0x1800013d4  jmp     short loc_180001370
```
