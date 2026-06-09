# TpmTransportSpbI2CDevice::I2CWriteRegister(uchar,uchar const *,uint,_LARGE_INTEGER,bool)

- ea: `0x140025c20`
- end: `0x140025d56`
- name: `?I2CWriteRegister@TpmTransportSpbI2CDevice@@IEAAJEPEBEIT_LARGE_INTEGER@@_N@Z`
- size: `310`
- prototype: `__int64 __fastcall(TpmTransportSpbI2CDevice *__hidden this, unsigned __int8, const unsigned __int8 *, unsigned int, union _LARGE_INTEGER, bool)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x140025834`
- `0x140025960`
- `0x140025a54`
- `0x140027400`

## callees

- `0x1400078b8`
- `0x140025c20`
- `0x140026a68`
- `0x140039740`
- `0x140039840`
- `0x140039b40`

## import_xrefs

- `ntoskrnl!KeQueryTimeIncrement` at `0x140025cd3`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140025d1f`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140025cd3`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140025d1f`

## pseudocode

```c
__int64 __fastcall TpmTransportSpbI2CDevice::I2CWriteRegister(
        TpmTransportSpbI2CDevice *this,
        char a2,
        const unsigned __int8 *a3,
        unsigned int a4)
{
  size_t v5; // rbp
  unsigned int v8; // esi
  char v9; // al
  __int64 v10; // rbx
  unsigned int i; // ebx
  __int64 v12; // rbx
  __int64 TimeIncrement; // rcx
  __int64 result; // rax
  _BYTE v15[272]; // [rsp+20h] [rbp-148h] BYREF

  v5 = a4;
  memset(v15, 0, 0x101u);
  if ( (unsigned int)v5 <= 0x100 )
  {
    v15[0] = a2;
    memmove(&v15[1], a3, v5);
    v9 = *((_BYTE *)this + 40);
    if ( v9 == 114 && *((_BYTE *)this + 26) || v9 == 119 && *((_BYTE *)this + 27) )
    {
      do
        v10 = MEMORY[0xFFFFF78000000320];
      while ( *((_QWORD *)this + 6) + *((_QWORD *)this + 4) - v10 * KeQueryTimeIncrement() > 0 );
    }
    *((_BYTE *)this + 40) = 119;
    for ( i = 0; i <= 5; ++i )
    {
      v8 = TpmTransportSpbDevice::SPBWrite(this, v15, (int)v5 + 1);
      if ( v8 != -1073741810 )
        break;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_7dd49ddb627336f214b85aab2cfde8ce_Traceguids);
    v8 = -1073741434;
  }
  v12 = MEMORY[0xFFFFF78000000320];
  TimeIncrement = KeQueryTimeIncrement();
  result = v8;
  *((_QWORD *)this + 6) = v12 * TimeIncrement;
  return result;
}

```

## disassembly

```asm
0x140025c20  push    rbx
0x140025c22  push    rbp
0x140025c23  push    rsi
0x140025c24  push    rdi
0x140025c25  push    r14
0x140025c27  sub     rsp, 140h
0x140025c2e  mov     rax, cs:__security_cookie
0x140025c35  xor     rax, rsp
0x140025c38  mov     [rsp+168h+var_38], rax
0x140025c40  mov     rsi, r8
0x140025c43  mov     ebp, r9d
0x140025c46  mov     bl, dl
0x140025c48  mov     rdi, rcx
0x140025c4b  xor     edx, edx; Val
0x140025c4d  lea     rcx, [rsp+168h+var_148]; void *
0x140025c52  mov     r8d, 101h; Size
0x140025c58  call    memset
0x140025c5d  mov     r14, 0FFFFF78000000320h
0x140025c67  cmp     ebp, 100h
0x140025c6d  jbe     short loc_140025CA5
0x140025c6f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140025c76  lea     rax, WPP_GLOBAL_Control
0x140025c7d  cmp     rcx, rax
0x140025c80  jz      short loc_140025C9E
0x140025c82  mov     eax, [rcx+2Ch]
0x140025c85  test    al, 1
0x140025c87  jz      short loc_140025C9E
0x140025c89  mov     rcx, [rcx+18h]
0x140025c8d  lea     r8, WPP_7dd49ddb627336f214b85aab2cfde8ce_Traceguids
0x140025c94  mov     edx, 18h
0x140025c99  call    WPP_SF_
0x140025c9e  mov     esi, 0C0000186h
0x140025ca3  jmp     short loc_140025D1C
0x140025ca5  mov     r8, rbp; Size
0x140025ca8  mov     [rsp+168h+var_148], bl
0x140025cac  mov     rdx, rsi; Src
0x140025caf  lea     rcx, [rsp+168h+var_147]; void *
0x140025cb4  call    memmove
0x140025cb9  mov     al, [rdi+28h]
0x140025cbc  cmp     al, 72h ; 'r'
0x140025cbe  jnz     short loc_140025CC6
0x140025cc0  cmp     byte ptr [rdi+1Ah], 0
0x140025cc4  jnz     short loc_140025CD0
0x140025cc6  cmp     al, 77h ; 'w'
0x140025cc8  jnz     short loc_140025CF5
0x140025cca  cmp     byte ptr [rdi+1Bh], 0
0x140025cce  jz      short loc_140025CF5
0x140025cd0  mov     rbx, [r14]
0x140025cd3  call    cs:__imp_KeQueryTimeIncrement
0x140025cda  nop     dword ptr [rax+rax+00h]
0x140025cdf  mov     rcx, [rdi+20h]
0x140025ce3  mov     eax, eax
0x140025ce5  imul    rax, rbx
0x140025ce9  sub     rcx, rax
0x140025cec  add     rcx, [rdi+30h]
0x140025cf0  test    rcx, rcx
0x140025cf3  jg      short loc_140025CD0
0x140025cf5  mov     byte ptr [rdi+28h], 77h ; 'w'
0x140025cf9  xor     ebx, ebx
0x140025cfb  lea     r8d, [rbp+1]; unsigned int
0x140025cff  mov     rcx, rdi; this
0x140025d02  lea     rdx, [rsp+168h+var_148]; void *
0x140025d07  call    ?SPBWrite@TpmTransportSpbDevice@@IEAAJPEAXI@Z; TpmTransportSpbDevice::SPBWrite(void *,uint)
0x140025d0c  mov     esi, eax
0x140025d0e  cmp     eax, 0C000000Eh
0x140025d13  jnz     short loc_140025D1C
0x140025d15  inc     ebx
0x140025d17  cmp     ebx, 5
0x140025d1a  jbe     short loc_140025CFB
0x140025d1c  mov     rbx, [r14]
0x140025d1f  call    cs:__imp_KeQueryTimeIncrement
0x140025d26  nop     dword ptr [rax+rax+00h]
0x140025d2b  mov     ecx, eax
0x140025d2d  mov     eax, esi
0x140025d2f  imul    rcx, rbx
0x140025d33  mov     [rdi+30h], rcx
0x140025d37  mov     rcx, [rsp+168h+var_38]
0x140025d3f  xor     rcx, rsp; StackCookie
0x140025d42  call    __security_check_cookie
0x140025d47  add     rsp, 140h
0x140025d4e  pop     r14
0x140025d50  pop     rdi
0x140025d51  pop     rsi
0x140025d52  pop     rbp
0x140025d53  pop     rbx
0x140025d54  retn
```
