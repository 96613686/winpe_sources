# CControlPacket::AddVariable<ulong>(ushort const *,ushort const *,ulong,ulong,ulong)

- ea: `0x1800119d4`
- end: `0x180011a88`
- name: `??$AddVariable@K@CControlPacket@@QEAAKPEBG0KKK@Z`
- size: `180`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `12`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180003838`
- `0x180007b18`
- `0x18001231c`
- `0x180012510`
- `0x180012d80`
- `0x1800139a8`
- `0x180013adc`
- `0x180014d4c`
- `0x180014df0`
- `0x180014e2c`
- `0x180014e68`
- `0x180014f60`

## callees

- `0x1800119d4`
- `0x180011f2c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180011a69`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011a69`
- `KERNEL32!GetLastError` at `0x180011a45`
- `KERNEL32!GetLastError` at `0x180011a45`
- `WDSCSL!WdsCpParameterAdd` at `0x180011a31`
- `WDSCSL!WdsCpParameterAdd` at `0x180011a31`

## pseudocode

```c
__int64 __fastcall CControlPacket::AddVariable<unsigned long>(
        CControlPacket *a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        __int64 a5,
        int a6)
{
  DWORD LastError; // ebx
  int v8; // edi
  _DWORD *v9; // rcx
  unsigned __int16 *v11; // [rsp+30h] [rbp-18h] BYREF

  LastError = 0;
  v11 = 0;
  if ( a4 != -1 || a3 )
  {
    v8 = 1;
    LastError = CControlPacket::ConstructName(a1, a2, a3, a4, &v11);
    if ( LastError )
    {
LABEL_10:
      if ( v11 )
        operator delete(v11);
      return LastError;
    }
    a2 = v11;
  }
  else
  {
    v11 = a2;
    v8 = 0;
  }
  v9 = (_DWORD *)WdsCpParameterAdd(*((_QWORD *)a1 + 1), a2, 4);
  if ( v9 )
    *v9 = a6;
  else
    LastError = GetLastError();
  if ( v8 )
    goto LABEL_10;
  return LastError;
}

```

## disassembly

```asm
0x1800119d4  mov     rax, rsp
0x1800119d7  mov     [rax+8], rbx
0x1800119db  mov     [rax+10h], rsi
0x1800119df  push    rdi
0x1800119e0  sub     rsp, 40h
0x1800119e4  xor     ebx, ebx
0x1800119e6  mov     rsi, rcx
0x1800119e9  and     [rax-18h], rbx
0x1800119ed  cmp     r9d, 0FFFFFFFFh
0x1800119f1  jnz     short loc_180011A00
0x1800119f3  test    r8, r8
0x1800119f6  jnz     short loc_180011A00
0x1800119f8  mov     [rax-18h], rdx
0x1800119fc  xor     edi, edi
0x1800119fe  jmp     short loc_180011A1F
0x180011a00  lea     rax, [rsp+48h+var_18]
0x180011a05  mov     edi, 1
0x180011a0a  mov     [rsp+48h+var_28], rax; unsigned __int16 **
0x180011a0f  call    ?ConstructName@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::ConstructName(ushort const *,ushort const *,ulong,ushort * *)
0x180011a14  mov     ebx, eax
0x180011a16  test    eax, eax
0x180011a18  jnz     short loc_180011A5F
0x180011a1a  mov     rdx, [rsp+48h+var_18]
0x180011a1f  mov     rcx, [rsi+8]
0x180011a23  mov     r8d, 4
0x180011a29  and     dword ptr [rsp+48h+var_28], 0
0x180011a2e  mov     r9d, r8d
0x180011a31  call    cs:__imp_WdsCpParameterAdd
0x180011a38  nop     dword ptr [rax+rax+00h]
0x180011a3d  mov     rcx, rax
0x180011a40  test    rax, rax
0x180011a43  jnz     short loc_180011A55
0x180011a45  call    cs:__imp_GetLastError
0x180011a4c  nop     dword ptr [rax+rax+00h]
0x180011a51  mov     ebx, eax
0x180011a53  jmp     short loc_180011A5B
0x180011a55  mov     eax, [rsp+48h+arg_28]
0x180011a59  mov     [rcx], eax
0x180011a5b  test    edi, edi
0x180011a5d  jz      short loc_180011A75
0x180011a5f  mov     rcx, [rsp+48h+var_18]
0x180011a64  test    rcx, rcx
0x180011a67  jz      short loc_180011A75
0x180011a69  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180011a70  nop     dword ptr [rax+rax+00h]
0x180011a75  mov     rsi, [rsp+48h+arg_8]
0x180011a7a  mov     eax, ebx
0x180011a7c  mov     rbx, [rsp+48h+arg_0]
0x180011a81  add     rsp, 40h
0x180011a85  pop     rdi
0x180011a86  retn
```
