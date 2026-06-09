# EapControls::InitOneXUIControls(void)

- ea: `0x180008cdc`
- end: `0x180008e78`
- name: `?InitOneXUIControls@EapControls@@QEAAJXZ`
- size: `412`
- prototype: `__int64 __fastcall(EapControls *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a7f8`
- `0x18000c824`

## callees

- `0x180001e26`
- `0x180008944`
- `0x180008cdc`
- `0x18001561c`

## import_xrefs

- `USER32!SendMessageW` at `0x180008e1e`
- `USER32!SendMessageW` at `0x180008e1e`
- `wlanapi!WpFreeMemory` at `0x180008e50`
- `wlanapi!WpFreeMemory` at `0x180008e50`
- `wlanapi!WpAllocMemory` at `0x180008da8`
- `wlanapi!WpAllocMemory` at `0x180008da8`
- `OneX!OneXFreeMemory` at `0x180008dd4`
- `OneX!OneXFreeMemory` at `0x180008e3e`
- `OneX!OneXFreeMemory` at `0x180008dd4`
- `OneX!OneXFreeMemory` at `0x180008e3e`
- `OneX!OneXCreateDefaultProfile` at `0x180008d70`
- `OneX!OneXCreateDefaultProfile` at `0x180008d70`
- `OneX!OneXDeInitialize` at `0x180008d7e`
- `OneX!OneXDeInitialize` at `0x180008d7e`
- `OneX!OneXInitialize` at `0x180008d52`
- `OneX!OneXInitialize` at `0x180008d52`

## pseudocode

```c
__int64 __fastcall EapControls::InitOneXUIControls(EapControls *this)
{
  __int64 v1; // rax
  signed int inited; // ebx
  __int64 v3; // r14
  __int64 v5; // rdx
  __int64 v6; // rsi
  BOOL v7; // eax
  _DWORD *v8; // rdi
  bool v9; // sf
  _DWORD *v10; // rax
  int v11; // r8d
  int v12; // eax
  size_t Size; // [rsp+60h] [rbp+30h] BYREF
  void *Src; // [rsp+68h] [rbp+38h] BYREF
  __int64 v16; // [rsp+70h] [rbp+40h] BYREF

  v1 = *(_QWORD *)this;
  inited = 0;
  LODWORD(Size) = 0;
  v3 = 0;
  Src = 0;
  v16 = 0;
  v5 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 40) + 552LL) + 32LL);
  v6 = *(_QWORD *)(v5 + 424);
  v7 = *(_DWORD *)(v6 + 32) || *(_DWORD *)(v5 + 436);
  if ( *((_DWORD *)this + 6) )
    return (unsigned int)inited;
  if ( !v7 || !*(_DWORD *)(v6 + 40) || (v8 = *(_DWORD **)(v6 + 48)) == 0 )
  {
    inited = OneXInitialize(0);
    if ( !inited )
    {
      inited = OneXCreateDefaultProfile(1, 0, &Size, &Src, 0);
      if ( !inited )
        inited = OneXDeInitialize(0);
    }
    v9 = inited < 0;
    if ( inited > 0 )
    {
      inited = (unsigned __int16)inited | 0x80070000;
      v9 = inited < 0;
    }
    if ( v9 )
      goto LABEL_29;
    if ( !Src )
      return (unsigned int)inited;
    v10 = (_DWORD *)WpAllocMemory((unsigned int)Size);
    v8 = v10;
    if ( !v10 )
    {
      inited = -2147024882;
LABEL_29:
      *(_DWORD *)(v6 + 40) = 0;
      *(_QWORD *)(v6 + 48) = 0;
      return (unsigned int)inited;
    }
    memcpy_0(v10, Src, (unsigned int)Size);
    OneXFreeMemory(Src);
    *(_DWORD *)(v6 + 40) = Size;
    *(_QWORD *)(v6 + 48) = v8;
  }
  if ( (v8[2] & 1) != 0 )
  {
    v11 = v8[3];
  }
  else
  {
    v12 = OneXFillProfileDefaults(this, v8, &v16);
    v3 = v16;
    if ( v12 )
      goto LABEL_24;
    v11 = *(_DWORD *)(v16 + 12);
  }
  SendMessageW(*((HWND *)this + 5), 0xF1u, ((unsigned int)~v11 >> 1) & 1, 0);
  *((_DWORD *)this + 6) = 1;
  inited = EapControls::InitEapData(this);
LABEL_24:
  if ( v3 )
    OneXFreeMemory(v3);
  if ( inited < 0 )
  {
    if ( v8 )
      WpFreeMemory(v8);
    goto LABEL_29;
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180008cdc  mov     [rsp-28h+arg_18], rbx
0x180008ce1  push    rbp
0x180008ce2  push    rsi
0x180008ce3  push    rdi
0x180008ce4  push    r14
0x180008ce6  push    r15
0x180008ce8  mov     rbp, rsp
0x180008ceb  sub     rsp, 30h
0x180008cef  mov     rax, [rcx]
0x180008cf2  xor     ebx, ebx
0x180008cf4  mov     dword ptr [rbp+Size], ebx
0x180008cf7  xor     r14d, r14d
0x180008cfa  mov     [rbp+Src], rbx
0x180008cfe  mov     r15, rcx
0x180008d01  mov     [rbp+arg_10], r14
0x180008d05  mov     rdx, [rax+28h]
0x180008d09  mov     rax, [rdx+228h]
0x180008d10  mov     rdx, [rax+20h]
0x180008d14  mov     rsi, [rdx+1A8h]
0x180008d1b  cmp     [rsi+20h], ebx
0x180008d1e  jnz     short loc_180008D2C
0x180008d20  cmp     [rdx+1B4h], ebx
0x180008d26  jnz     short loc_180008D2C
0x180008d28  xor     eax, eax
0x180008d2a  jmp     short loc_180008D31
0x180008d2c  mov     eax, 1
0x180008d31  cmp     [rcx+18h], ebx
0x180008d34  jnz     loc_180008E65
0x180008d3a  test    eax, eax
0x180008d3c  jz      short loc_180008D50
0x180008d3e  cmp     [rsi+28h], ebx
0x180008d41  jz      short loc_180008D50
0x180008d43  mov     rdi, [rsi+30h]
0x180008d47  test    rdi, rdi
0x180008d4a  jnz     loc_180008DE4
0x180008d50  xor     ecx, ecx
0x180008d52  call    cs:__imp_OneXInitialize
0x180008d58  mov     ebx, eax
0x180008d5a  test    eax, eax
0x180008d5c  jnz     short loc_180008D86
0x180008d5e  lea     r9, [rbp+Src]
0x180008d62  mov     [rsp+30h+var_10], r14
0x180008d67  lea     r8, [rbp+Size]
0x180008d6b  xor     edx, edx
0x180008d6d  lea     ecx, [rax+1]
0x180008d70  call    cs:__imp_OneXCreateDefaultProfile
0x180008d76  mov     ebx, eax
0x180008d78  test    eax, eax
0x180008d7a  jnz     short loc_180008D86
0x180008d7c  xor     ecx, ecx
0x180008d7e  call    cs:__imp_OneXDeInitialize
0x180008d84  mov     ebx, eax
0x180008d86  test    ebx, ebx
0x180008d88  jle     short loc_180008D95
0x180008d8a  movzx   ebx, bx
0x180008d8d  or      ebx, 80070000h
0x180008d93  test    ebx, ebx
0x180008d95  js      loc_180008E56
0x180008d9b  cmp     [rbp+Src], r14
0x180008d9f  jz      loc_180008E65
0x180008da5  mov     ecx, dword ptr [rbp+Size]
0x180008da8  call    cs:__imp_WpAllocMemory
0x180008dae  mov     rdi, rax
0x180008db1  test    rax, rax
0x180008db4  jnz     short loc_180008DC0
0x180008db6  mov     ebx, 8007000Eh
0x180008dbb  jmp     loc_180008E56
0x180008dc0  mov     r8d, dword ptr [rbp+Size]; Size
0x180008dc4  mov     rcx, rdi; void *
0x180008dc7  mov     rdx, [rbp+Src]; Src
0x180008dcb  call    memcpy_0
0x180008dd0  mov     rcx, [rbp+Src]
0x180008dd4  call    cs:__imp_OneXFreeMemory
0x180008dda  mov     eax, dword ptr [rbp+Size]
0x180008ddd  mov     [rsi+28h], eax
0x180008de0  mov     [rsi+30h], rdi
0x180008de4  test    byte ptr [rdi+8], 1
0x180008de8  jz      short loc_180008DF0
0x180008dea  mov     r8d, [rdi+0Ch]
0x180008dee  jmp     short loc_180008E08
0x180008df0  lea     r8, [rbp+arg_10]
0x180008df4  mov     rdx, rdi
0x180008df7  call    OneXFillProfileDefaults
0x180008dfc  mov     r14, [rbp+arg_10]
0x180008e00  test    eax, eax
0x180008e02  jnz     short loc_180008E36
0x180008e04  mov     r8d, [r14+0Ch]
0x180008e08  mov     rcx, [r15+28h]; hWnd
0x180008e0c  not     r8d
0x180008e0f  shr     r8, 1
0x180008e12  xor     r9d, r9d; lParam
0x180008e15  and     r8d, 1; wParam
0x180008e19  mov     edx, 0F1h; Msg
0x180008e1e  call    cs:__imp_SendMessageW
0x180008e24  mov     rcx, r15; this
0x180008e27  mov     dword ptr [r15+18h], 1
0x180008e2f  call    ?InitEapData@EapControls@@QEAAJXZ; EapControls::InitEapData(void)
0x180008e34  mov     ebx, eax
0x180008e36  test    r14, r14
0x180008e39  jz      short loc_180008E44
0x180008e3b  mov     rcx, r14
0x180008e3e  call    cs:__imp_OneXFreeMemory
0x180008e44  test    ebx, ebx
0x180008e46  jns     short loc_180008E65
0x180008e48  test    rdi, rdi
0x180008e4b  jz      short loc_180008E56
0x180008e4d  mov     rcx, rdi
0x180008e50  call    cs:__imp_WpFreeMemory
0x180008e56  mov     dword ptr [rsi+28h], 0
0x180008e5d  mov     qword ptr [rsi+30h], 0
0x180008e65  mov     eax, ebx
0x180008e67  mov     rbx, [rsp+30h+arg_18]
0x180008e6c  add     rsp, 30h
0x180008e70  pop     r15
0x180008e72  pop     r14
0x180008e74  pop     rdi
0x180008e75  pop     rsi
0x180008e76  pop     rbp
0x180008e77  retn
```
