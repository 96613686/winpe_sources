# NtCreateWorkerFactory

- ea: `0x1400ad0a4`
- end: `0x1400ad2d5`
- name: `NtCreateWorkerFactory`
- size: `561`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x140002ef0`
- `0x14002985c`
- `0x14002c64c`
- `0x140033a00`
- `0x140037e84`
- `0x1400a1128`
- `0x1400a18a0`
- `0x1400ad0a4`
- `0x1400eff90`
- `0x1400f0300`
- `0x1400fc664`
- `0x1400fc7c0`

## pseudocode

```c
__int64 __fastcall NtCreateWorkerFactory(
        _QWORD *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        int a8,
        __int64 a9,
        __int64 a10)
{
  _QWORD *StackBase; // rsi
  __int64 result; // rax
  _QWORD *v14; // rbx
  __int64 v15; // r15
  __int64 v16; // r12
  PVOID *v17; // rcx
  __int64 ULong64FromUser; // rdi
  __int64 v19; // rcx
  int WorkerFactory; // esi
  __int64 v21; // rcx
  _QWORD *v22; // [rsp+50h] [rbp-48h] BYREF
  __int64 v23; // [rsp+58h] [rbp-40h] BYREF
  __int64 v24; // [rsp+60h] [rbp-38h]

  v23 = 0;
  v22 = 0;
  StackBase = KeGetPcr()->NtTib.StackBase;
  if ( StackBase )
    StackBase = (_QWORD *)StackBase[10];
  if ( a5 != -1 || !StackBase )
    return 3221225659LL;
  result = SkobCreateObjectEx(0, (__int64)&SkeWorkerFactoryObjectType, 0, &v22);
  if ( (int)result >= 0 )
  {
    a5 = 0;
    v14 = v22;
    v22[3] = StackBase;
    v14[4] = a6;
    v14[5] = a7;
    v15 = a10;
    v14[7] = a10;
    v16 = a9;
    v14[6] = a9;
    v14[2] = 0;
    SkpspLockProcessExclusive(StackBase);
    v17 = (PVOID *)StackBase[48];
    if ( *v17 != StackBase + 47 )
      __fastfail(3u);
    ULong64FromUser = 0;
    v24 = 0;
    *v14 = StackBase + 47;
    v14[1] = v17;
    *v17 = v14;
    StackBase[48] = v14;
    SkpspUnlockProcessExclusive(StackBase);
    WorkerFactory = SkobReserveHandle(0, &a5);
    if ( WorkerFactory >= 0 )
    {
      LOBYTE(v19) = 1;
      WorkerFactory = SkobReserveHandle(v19, &v23);
      if ( WorkerFactory >= 0 )
      {
        v21 = v23;
        v14[2] = v23;
        WorkerFactory = NkCreateWorkerFactory(
                          a1,
                          a2,
                          a3,
                          a4,
                          -1,
                          v21 & 0xFFFFFFFFFFFFFFFLL | 0x1000000000000000LL,
                          v21 & 0xFFFFFFFFFFFFFFFLL | 0x1000000000000000LL,
                          a8,
                          v16,
                          v15);
        if ( WorkerFactory >= 0 )
        {
          ULong64FromUser = RtlReadULong64FromUser(a1);
          v24 = ULong64FromUser;
          RtlWriteULong64ToUser(a1, a5);
          SkobMakeReservedHandleValid(a5, v14, ULong64FromUser);
        }
      }
    }
    if ( WorkerFactory < 0 )
    {
      if ( ULong64FromUser )
        NkClose(ULong64FromUser);
      if ( a5 )
        SkobDeleteReservedHandle(a5);
    }
    SkobDereferenceObject((__int64)v14);
    return (unsigned int)WorkerFactory;
  }
  return result;
}

```

## disassembly

```asm
0x1400ad0a4  mov     rax, rsp
0x1400ad0a7  mov     [rax+8], rbx
0x1400ad0ab  mov     [rax+20h], rsi
0x1400ad0af  mov     [rax+18h], r8
0x1400ad0b3  mov     [rax+10h], edx
0x1400ad0b6  push    rdi
0x1400ad0b7  push    r12
0x1400ad0b9  push    r13
0x1400ad0bb  push    r14
0x1400ad0bd  push    r15
0x1400ad0bf  sub     rsp, 70h
0x1400ad0c3  mov     r13, r9
0x1400ad0c6  mov     r14, rcx
0x1400ad0c9  mov     qword ptr [rax-40h], 0
0x1400ad0d1  mov     qword ptr [rax-48h], 0
0x1400ad0d9  mov     rsi, gs:8
0x1400ad0e2  test    rsi, rsi
0x1400ad0e5  jz      short loc_1400AD0EB
0x1400ad0e7  mov     rsi, [rsi+50h]
0x1400ad0eb  cmp     [rsp+98h+arg_20], 0FFFFFFFFFFFFFFFFh
0x1400ad0f4  jnz     loc_1400AD2B5
0x1400ad0fa  test    rsi, rsi
0x1400ad0fd  jz      loc_1400AD2B5
0x1400ad103  lea     r9, [rsp+98h+var_48]
0x1400ad108  xor     r8d, r8d
0x1400ad10b  lea     rdx, SkeWorkerFactoryObjectType
0x1400ad112  xor     ecx, ecx
0x1400ad114  call    SkobCreateObjectEx
0x1400ad119  test    eax, eax
0x1400ad11b  js      loc_1400AD2BA
0x1400ad121  mov     [rsp+98h+arg_20], 0
0x1400ad12d  mov     rbx, [rsp+98h+var_48]
0x1400ad132  mov     [rbx+18h], rsi
0x1400ad136  mov     rax, [rsp+98h+arg_28]
0x1400ad13e  mov     [rbx+20h], rax
0x1400ad142  mov     rax, [rsp+98h+arg_30]
0x1400ad14a  mov     [rbx+28h], rax
0x1400ad14e  mov     r15, [rsp+98h+arg_48]
0x1400ad156  mov     [rbx+38h], r15
0x1400ad15a  mov     r12, [rsp+98h+arg_40]
0x1400ad162  mov     [rbx+30h], r12
0x1400ad166  mov     qword ptr [rbx+10h], 0
0x1400ad16e  mov     rcx, rsi
0x1400ad171  call    SkpspLockProcessExclusive
0x1400ad176  lea     rax, [rsi+178h]
0x1400ad17d  mov     rcx, [rax+8]
0x1400ad181  cmp     [rcx], rax
0x1400ad184  jz      short loc_1400AD18D
0x1400ad186  mov     ecx, 3
0x1400ad18b  int     29h; Win8: RtlFailFast(ecx)
0x1400ad18d  xor     edi, edi
0x1400ad18f  mov     [rsp+98h+var_38], rdi
0x1400ad194  mov     [rbx], rax
0x1400ad197  mov     [rbx+8], rcx
0x1400ad19b  mov     [rcx], rbx
0x1400ad19e  mov     [rax+8], rbx
0x1400ad1a2  mov     rcx, rsi
0x1400ad1a5  call    SkpspUnlockProcessExclusive
0x1400ad1aa  lea     rdx, [rsp+98h+arg_20]
0x1400ad1b2  xor     ecx, ecx
0x1400ad1b4  call    SkobReserveHandle
0x1400ad1b9  mov     esi, eax
0x1400ad1bb  test    eax, eax
0x1400ad1bd  js      loc_1400AD286
0x1400ad1c3  lea     rdx, [rsp+98h+var_40]
0x1400ad1c8  mov     cl, 1
0x1400ad1ca  call    SkobReserveHandle
0x1400ad1cf  mov     esi, eax
0x1400ad1d1  test    eax, eax
0x1400ad1d3  js      loc_1400AD286
0x1400ad1d9  mov     rcx, [rsp+98h+var_40]
0x1400ad1de  mov     [rbx+10h], rcx
0x1400ad1e2  mov     rax, 0FFFFFFFFFFFFFFFh
0x1400ad1ec  and     rcx, rax
0x1400ad1ef  mov     rax, 1000000000000000h
0x1400ad1f9  or      rcx, rax
0x1400ad1fc  mov     [rsp+98h+var_50], r15
0x1400ad201  mov     [rsp+98h+var_58], r12
0x1400ad206  mov     eax, [rsp+98h+arg_38]
0x1400ad20d  mov     [rsp+98h+var_60], eax
0x1400ad211  mov     [rsp+98h+var_68], rcx
0x1400ad216  mov     [rsp+98h+var_70], rcx
0x1400ad21b  mov     [rsp+98h+var_78], 0FFFFFFFFFFFFFFFFh
0x1400ad224  mov     r9, r13
0x1400ad227  mov     r8, [rsp+98h+arg_10]
0x1400ad22f  mov     edx, [rsp+98h+arg_8]
0x1400ad236  mov     rcx, r14
0x1400ad239  call    NkCreateWorkerFactory
0x1400ad23e  mov     esi, eax
0x1400ad240  test    eax, eax
0x1400ad242  js      short loc_1400AD286
0x1400ad244  mov     rcx, r14
0x1400ad247  call    RtlReadULong64FromUser
0x1400ad24c  mov     rdi, rax
0x1400ad24f  mov     [rsp+98h+var_38], rax
0x1400ad254  mov     rdx, [rsp+98h+arg_20]
0x1400ad25c  mov     rcx, r14
0x1400ad25f  call    RtlWriteULong64ToUser
0x1400ad264  nop
0x1400ad265  mov     r8, rdi
0x1400ad268  mov     rdx, rbx
0x1400ad26b  mov     rcx, [rsp+98h+arg_20]
0x1400ad273  call    SkobMakeReservedHandleValid
0x1400ad278  jmp     short loc_1400AD286
0x1400ad27a  mov     esi, eax
0x1400ad27c  mov     rdi, [rsp+98h+var_38]
0x1400ad281  mov     rbx, [rsp+98h+var_48]
0x1400ad286  test    esi, esi
0x1400ad288  jns     short loc_1400AD2A9
0x1400ad28a  test    rdi, rdi
0x1400ad28d  jz      short loc_1400AD297
0x1400ad28f  mov     rcx, rdi
0x1400ad292  call    NkClose
0x1400ad297  mov     rcx, [rsp+98h+arg_20]
0x1400ad29f  test    rcx, rcx
0x1400ad2a2  jz      short loc_1400AD2A9
0x1400ad2a4  call    SkobDeleteReservedHandle
0x1400ad2a9  mov     rcx, rbx
0x1400ad2ac  call    SkobDereferenceObject
0x1400ad2b1  mov     eax, esi
0x1400ad2b3  jmp     short loc_1400AD2BA
0x1400ad2b5  mov     eax, 0C00000BBh
0x1400ad2ba  lea     r11, [rsp+98h+var_28]
0x1400ad2bf  mov     rbx, [r11+30h]
0x1400ad2c3  mov     rsi, [r11+48h]
0x1400ad2c7  mov     rsp, r11
0x1400ad2ca  pop     r15
0x1400ad2cc  pop     r14
0x1400ad2ce  pop     r13
0x1400ad2d0  pop     r12
0x1400ad2d2  pop     rdi
0x1400ad2d3  retn
```
