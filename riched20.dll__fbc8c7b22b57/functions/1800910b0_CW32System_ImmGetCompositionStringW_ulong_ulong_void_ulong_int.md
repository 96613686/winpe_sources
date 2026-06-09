# CW32System::ImmGetCompositionStringW(ulong,ulong,void *,ulong,int)

- ea: `0x1800910b0`
- end: `0x18009114f`
- name: `?ImmGetCompositionStringW@CW32System@@SAJKKPEAXKH@Z`
- size: `159`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, void *, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180066898`

## callees

- `0x1800910b0`
- `0x180092fb0`
- `0x180095010`

## string_xrefs

- `0x18009111a`: `ImmGetCompositionStringW`

## pseudocode

```c
__int64 __fastcall CW32System::ImmGetCompositionStringW(
        unsigned int a1,
        unsigned int a2,
        void *a3,
        unsigned int a4,
        int a5)
{
  __int64 (__fastcall *v10)(_QWORD, _QWORD, void *, _QWORD); // rax

  if ( a5 )
  {
    (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)qword_1800A7598 + 160LL))(qword_1800A7598, a1, a2);
    return 0;
  }
  else
  {
    v10 = (__int64 (__fastcall *)(_QWORD, _QWORD, void *, _QWORD))qword_1800A71D8;
    if ( !qword_1800A71D8 )
    {
      SetIMEProcAddr(&qword_1800A71D8, 0, "ImmGetCompositionStringW");
      v10 = (__int64 (__fastcall *)(_QWORD, _QWORD, void *, _QWORD))qword_1800A71D8;
    }
    return v10(a1, a2, a3, a4);
  }
}

```

## disassembly

```asm
0x1800910b0  mov     r11, rsp
0x1800910b3  push    rbx
0x1800910b4  push    rbp
0x1800910b5  push    rsi
0x1800910b6  push    rdi
0x1800910b7  sub     rsp, 48h
0x1800910bb  cmp     [rsp+68h+arg_20], 0
0x1800910c3  mov     ebx, r9d
0x1800910c6  mov     rdi, r8
0x1800910c9  mov     esi, edx
0x1800910cb  mov     ebp, ecx
0x1800910cd  jz      short loc_18009110E
0x1800910cf  mov     rcx, cs:qword_1800A7598
0x1800910d6  lea     rdx, [r11+28h]
0x1800910da  mov     [r11-40h], r8
0x1800910de  mov     r8d, esi
0x1800910e1  mov     dword ptr [r11+28h], 0
0x1800910e9  mov     [r11-48h], rdx
0x1800910ed  mov     edx, ebp
0x1800910ef  mov     rax, [rcx]
0x1800910f2  mov     rax, [rax+0A0h]
0x1800910f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800910fe  xor     ecx, ecx
0x180091100  test    eax, eax
0x180091102  cmovns  ecx, [rsp+68h+arg_20]
0x18009110a  mov     eax, ecx
0x18009110c  jmp     short loc_180091145
0x18009110e  mov     rax, cs:qword_1800A71D8
0x180091115  test    rax, rax
0x180091118  jnz     short loc_180091136
0x18009111a  lea     r8, aImmgetcomposit; "ImmGetCompositionStringW"
0x180091121  xor     edx, edx
0x180091123  lea     rcx, qword_1800A71D8
0x18009112a  call    SetIMEProcAddr
0x18009112f  mov     rax, cs:qword_1800A71D8
0x180091136  mov     r9d, ebx
0x180091139  mov     r8, rdi
0x18009113c  mov     edx, esi
0x18009113e  mov     ecx, ebp
0x180091140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091145  add     rsp, 48h
0x180091149  pop     rdi
0x18009114a  pop     rsi
0x18009114b  pop     rbp
0x18009114c  pop     rbx
0x18009114d  retn
```
