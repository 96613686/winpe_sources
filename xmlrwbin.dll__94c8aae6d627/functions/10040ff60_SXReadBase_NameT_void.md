# SXReadBase::NameT(void)

- ea: `0x10040ff60`
- end: `0x10041000a`
- name: `?NameT@SXReadBase@@IEAAXXZ`
- size: `170`
- prototype: `void __fastcall(SXTokenTable **this)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x10040edb0`
- `0x10040f700`
- `0x1004101e0`

## callees

- `0x100401350`
- `0x100406be0`
- `0x10040ff60`
- `0x100410e60`
- `0x100411000`
- `0x1004130c0`

## pseudocode

```c
void __fastcall SXReadBase::NameT(SXTokenTable **this)
{
  unsigned int Mb32; // esi
  unsigned int v3; // edi
  unsigned int v4; // eax
  wchar_t *WCharBuffer; // rbp

  Mb32 = SXReadBase::GetMb32((SXReadBase *)this);
  v3 = 2 * Mb32;
  if ( 2 * Mb32 < Mb32 )
  {
    MXRRaiseException(-2147352566);
    __debugbreak();
  }
  v4 = *((_DWORD *)this + 174);
  if ( v4 && v3 > v4 )
  {
    MXRRaiseException(-1072897499);
    JUMPOUT(0x100410009LL);
  }
  _mm_lfence();
  _mm_lfence();
  if ( v3 )
  {
    WCharBuffer = SXReadBase::GetWCharBuffer((SXReadBase *)this, 1, Mb32);
    SXReadBase::GetBytes((SXReadBase *)this, (unsigned __int8 *)WCharBuffer, v3);
  }
  else
  {
    WCharBuffer = SXReadBase::GetWCharBuffer((SXReadBase *)this, 1, 2u);
  }
  SXTokenTable::putName(this[90], WCharBuffer, Mb32);
}

```

## disassembly

```asm
0x10040ff60  mov     [rsp+arg_8], rbx
0x10040ff65  mov     [rsp+arg_10], rsi
0x10040ff6a  push    rdi
0x10040ff6b  sub     rsp, 20h
0x10040ff6f  mov     rbx, rcx
0x10040ff72  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x10040ff77  mov     esi, eax
0x10040ff79  lea     edi, [rax+rax]
0x10040ff7c  cmp     edi, eax
0x10040ff7e  jb      short loc_10040FFF4
0x10040ff80  mov     eax, [rbx+2B8h]
0x10040ff86  test    eax, eax
0x10040ff88  jz      short loc_10040FF8E
0x10040ff8a  cmp     edi, eax
0x10040ff8c  ja      short loc_10040FFFF
0x10040ff8e  mov     [rsp+28h+arg_0], rbp
0x10040ff93  lfence
0x10040ff96  lfence
0x10040ff99  mov     edx, 1; int
0x10040ff9e  mov     rcx, rbx; this
0x10040ffa1  test    edi, edi
0x10040ffa3  jz      short loc_10040FFC0
0x10040ffa5  mov     r8d, esi; unsigned int
0x10040ffa8  call    ?GetWCharBuffer@SXReadBase@@IEAAPEA_WHK@Z; SXReadBase::GetWCharBuffer(int,ulong)
0x10040ffad  mov     r8d, edi; unsigned int
0x10040ffb0  mov     rdx, rax; unsigned __int8 *
0x10040ffb3  mov     rcx, rbx; this
0x10040ffb6  mov     rbp, rax
0x10040ffb9  call    ?GetBytes@SXReadBase@@IEAAXPEAEK@Z; SXReadBase::GetBytes(uchar *,ulong)
0x10040ffbe  jmp     short loc_10040FFCE
0x10040ffc0  mov     r8d, 2; unsigned int
0x10040ffc6  call    ?GetWCharBuffer@SXReadBase@@IEAAPEA_WHK@Z; SXReadBase::GetWCharBuffer(int,ulong)
0x10040ffcb  mov     rbp, rax
0x10040ffce  mov     rcx, [rbx+2D0h]; this
0x10040ffd5  mov     r8d, esi; unsigned int
0x10040ffd8  mov     rdx, rbp; wchar_t *
0x10040ffdb  mov     rbp, [rsp+28h+arg_0]
0x10040ffe0  mov     rbx, [rsp+28h+arg_8]
0x10040ffe5  mov     rsi, [rsp+28h+arg_10]
0x10040ffea  add     rsp, 20h
0x10040ffee  pop     rdi
0x10040ffef  jmp     ?putName@SXTokenTable@@QEAAXPEB_WK@Z; SXTokenTable::putName(wchar_t const *,ulong)
0x10040fff4  mov     ecx, 8002000Ah; int
0x10040fff9  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040fffe  int     3; Trap to Debugger
0x10040ffff  mov     ecx, 0C00CE225h; int
0x100410004  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
