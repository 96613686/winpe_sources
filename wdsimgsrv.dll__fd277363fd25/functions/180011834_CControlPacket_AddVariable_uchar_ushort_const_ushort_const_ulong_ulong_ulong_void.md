# CControlPacket::AddVariable<uchar>(ushort const *,ushort const *,ulong,ulong,ulong,void *)

- ea: `0x180011834`
- end: `0x1800118f6`
- name: `??$AddVariable@E@CControlPacket@@QEAAKPEBG0KKKPEAX@Z`
- size: `194`
- prototype: `__int64 __fastcall(CControlPacket *, unsigned __int16 *, const unsigned __int16 *, unsigned int, int, int, void *Src)`
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180010b84`
- `0x18001231c`
- `0x180012890`
- `0x180012a18`
- `0x180012d80`
- `0x180013170`
- `0x180013adc`

## callees

- `0x1800025e4`
- `0x180011834`
- `0x180011f2c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800118d7`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800118d7`
- `KERNEL32!GetLastError` at `0x1800118a3`
- `KERNEL32!GetLastError` at `0x1800118a3`
- `WDSCSL!WdsCpParameterAdd` at `0x180011892`
- `WDSCSL!WdsCpParameterAdd` at `0x180011892`

## pseudocode

```c
__int64 __fastcall CControlPacket::AddVariable<unsigned char>(
        CControlPacket *a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        int a5,
        int a6,
        void *Src)
{
  DWORD LastError; // ebx
  int v9; // edi
  void *v10; // rax
  unsigned __int16 *v12; // [rsp+30h] [rbp-18h] BYREF

  LastError = 0;
  v12 = 0;
  if ( a4 != -1 || a3 )
  {
    v9 = 1;
    LastError = CControlPacket::ConstructName(a1, a2, a3, a4, &v12);
    if ( LastError )
    {
LABEL_10:
      if ( v12 )
        operator delete(v12);
      return LastError;
    }
    a2 = v12;
  }
  else
  {
    v12 = a2;
    v9 = 0;
  }
  v10 = (void *)WdsCpParameterAdd(*((_QWORD *)a1 + 1), a2, 64);
  if ( v10 )
    memmove_0(v10, Src, 0x10u);
  else
    LastError = GetLastError();
  if ( v9 )
    goto LABEL_10;
  return LastError;
}

```

## disassembly

```asm
0x180011834  mov     rax, rsp
0x180011837  mov     [rax+8], rbx
0x18001183b  mov     [rax+10h], rsi
0x18001183f  push    rdi
0x180011840  sub     rsp, 40h
0x180011844  xor     ebx, ebx
0x180011846  mov     rsi, rcx
0x180011849  and     [rax-18h], rbx
0x18001184d  cmp     r9d, 0FFFFFFFFh
0x180011851  jnz     short loc_180011860
0x180011853  test    r8, r8
0x180011856  jnz     short loc_180011860
0x180011858  mov     [rax-18h], rdx
0x18001185c  xor     edi, edi
0x18001185e  jmp     short loc_18001187F
0x180011860  lea     rax, [rsp+48h+var_18]
0x180011865  mov     edi, 1
0x18001186a  mov     [rsp+48h+var_28], rax; unsigned __int16 **
0x18001186f  call    ?ConstructName@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::ConstructName(ushort const *,ushort const *,ulong,ushort * *)
0x180011874  mov     ebx, eax
0x180011876  test    eax, eax
0x180011878  jnz     short loc_1800118CD
0x18001187a  mov     rdx, [rsp+48h+var_18]
0x18001187f  mov     rcx, [rsi+8]
0x180011883  mov     r9d, 10h
0x180011889  and     dword ptr [rsp+48h+var_28], 0
0x18001188e  lea     r8d, [r9+30h]
0x180011892  call    cs:__imp_WdsCpParameterAdd
0x180011899  nop     dword ptr [rax+rax+00h]
0x18001189e  test    rax, rax
0x1800118a1  jnz     short loc_1800118B3
0x1800118a3  call    cs:__imp_GetLastError
0x1800118aa  nop     dword ptr [rax+rax+00h]
0x1800118af  mov     ebx, eax
0x1800118b1  jmp     short loc_1800118C9
0x1800118b3  mov     rdx, [rsp+48h+Src]; Src
0x1800118bb  mov     r8d, 10h; Size
0x1800118c1  mov     rcx, rax; void *
0x1800118c4  call    memmove_0
0x1800118c9  test    edi, edi
0x1800118cb  jz      short loc_1800118E3
0x1800118cd  mov     rcx, [rsp+48h+var_18]
0x1800118d2  test    rcx, rcx
0x1800118d5  jz      short loc_1800118E3
0x1800118d7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800118de  nop     dword ptr [rax+rax+00h]
0x1800118e3  mov     rsi, [rsp+48h+arg_8]
0x1800118e8  mov     eax, ebx
0x1800118ea  mov     rbx, [rsp+48h+arg_0]
0x1800118ef  add     rsp, 40h
0x1800118f3  pop     rdi
0x1800118f4  retn
```
