# WhitebalanceComponentSetHandler

- ea: `0x140027970`
- end: `0x140027df6`
- name: `WhitebalanceComponentSetHandler`
- size: `1158`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400051e4`
- `0x140008640`
- `0x140008f80`
- `0x1400274f8`
- `0x140027560`
- `0x14002765c`
- `0x140027970`

## pseudocode

```c
__int64 __fastcall WhitebalanceComponentSetHandler(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r8
  int NodeInfoAndValidate; // ebx
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  int v10; // edx
  __int64 v11; // rsi
  __int64 v12; // r14
  char v13; // r15
  char v15; // [rsp+20h] [rbp-50h]
  int v16; // [rsp+20h] [rbp-50h]
  int v17; // [rsp+20h] [rbp-50h]
  size_t Size; // [rsp+30h] [rbp-40h]
  size_t Sizea; // [rsp+30h] [rbp-40h]
  __int64 v20; // [rsp+50h] [rbp-20h] BYREF
  __int64 v21; // [rsp+58h] [rbp-18h] BYREF
  __int64 v22; // [rsp+60h] [rbp-10h] BYREF
  unsigned __int8 v23; // [rsp+B0h] [rbp+40h] BYREF
  int v24; // [rsp+B8h] [rbp+48h] BYREF
  int v25; // [rsp+C0h] [rbp+50h] BYREF
  unsigned __int16 v26; // [rsp+C8h] [rbp+58h] BYREF
  unsigned __int16 v27; // [rsp+CAh] [rbp+5Ah]

  v4 = *(unsigned int *)(a2 + 20);
  v23 = 0;
  LOBYTE(v24) = 0;
  LOBYTE(v25) = 0;
  v22 = 0;
  v21 = 0;
  v20 = 0;
  if ( (v4 & 0x10000000) == 0 )
  {
    NodeInfoAndValidate = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_dDD(WPP_GLOBAL_Control->AttachedDevice, 20, v4, 1821, -1073741811, v4);
    goto LABEL_47;
  }
  v15 = 5;
  NodeInfoAndValidate = GetNodeInfoAndValidate(a1, a2, a3, 12, v15, &v24, &v25, &v21, &v20, &v22);
  if ( NodeInfoAndValidate < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_47;
    v8 = 21;
    v9 = 1837;
    goto LABEL_10;
  }
  v10 = *(_DWORD *)(a3 + 32);
  if ( (v10 & 0xFFFF0000) != 0 || (*(_DWORD *)(a3 + 44) & 0xFFFF0000) != 0 )
  {
    NodeInfoAndValidate = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_dDdd(WPP_GLOBAL_Control->AttachedDevice);
  }
  else
  {
    v27 = *(_WORD *)(a3 + 44);
    v26 = v10;
    if ( (*(_DWORD *)(v22 + 48) & 1) == 0 )
    {
      LODWORD(Size) = 4;
      LOBYTE(v16) = v25;
      NodeInfoAndValidate = SubmitControlRequest(0x21u, 1u, 0xC00u, v24, v16, (unsigned __int8 *)&v26, Size, v21, v20);
      if ( NodeInfoAndValidate >= 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
          WPP_SF_dDD(WPP_GLOBAL_Control->AttachedDevice, 24, v26, 1877, v26, v27);
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        WPP_SF_dDDD(WPP_GLOBAL_Control->AttachedDevice, 23, v26, 1873, v26, v27, NodeInfoAndValidate);
      }
      goto LABEL_47;
    }
    v11 = v20;
    v12 = v21;
    v13 = v25;
    LODWORD(Size) = 1;
    LOBYTE(v16) = v25;
    NodeInfoAndValidate = SubmitControlRequest(0xA1u, 0x81u, 0xD00u, v24, v16, &v23, Size, v21, v20);
    if ( NodeInfoAndValidate < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_47;
      v8 = 25;
      v9 = 1894;
      goto LABEL_10;
    }
    if ( (*(_DWORD *)(a3 + 36) & 2) != 0 )
    {
      if ( v23 )
      {
        LODWORD(Sizea) = 1;
        v23 = 0;
        LOBYTE(v17) = v13;
        NodeInfoAndValidate = SubmitControlRequest(0x21u, 1u, 0xD00u, v24, v17, &v23, Sizea, v12, v11);
        if ( NodeInfoAndValidate < 0 )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_47;
          }
          v8 = 26;
          v9 = 1918;
          goto LABEL_10;
        }
      }
      LODWORD(Sizea) = 4;
      LOBYTE(v17) = v13;
      NodeInfoAndValidate = SubmitControlRequest(0x21u, 1u, 0xC00u, v24, v17, (unsigned __int8 *)&v26, Sizea, v12, v11);
      if ( NodeInfoAndValidate < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_47;
        v8 = 27;
        v9 = 1934;
        goto LABEL_10;
      }
    }
    else if ( !v23 )
    {
      LODWORD(Sizea) = 1;
      LOBYTE(v17) = v13;
      v23 = 1;
      NodeInfoAndValidate = SubmitControlRequest(0x21u, 1u, 0xD00u, v24, v17, &v23, Sizea, v12, v11);
      if ( NodeInfoAndValidate < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_47;
        v8 = 28;
        v9 = 1957;
LABEL_10:
        WPP_SF_dd(v7->AttachedDevice, v8, WPP_a7e72e311a673739a589ba7821720449_Traceguids, v9, NodeInfoAndValidate);
        goto LABEL_47;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_dDDD(WPP_GLOBAL_Control->AttachedDevice, 29, v27, 1963, v26, v27, *(_DWORD *)(a3 + 36));
  }
LABEL_47:
  *(_DWORD *)(a1 + 48) = NodeInfoAndValidate;
  return (unsigned int)NodeInfoAndValidate;
}

```

## disassembly

```asm
0x140027970  push    rbp
0x140027972  push    rbx
0x140027973  push    rsi
0x140027974  push    rdi
0x140027975  push    r13
0x140027977  push    r14
0x140027979  push    r15
0x14002797b  mov     rbp, rsp
0x14002797e  sub     rsp, 70h
0x140027982  xor     esi, esi
0x140027984  mov     rdi, r8
0x140027987  mov     r8d, [rdx+14h]
0x14002798b  mov     r13, rcx
0x14002798e  mov     [rbp+arg_0], sil
0x140027992  mov     byte ptr [rbp+arg_8], sil
0x140027996  mov     byte ptr [rbp+arg_10], sil
0x14002799a  mov     [rbp+var_10], rsi
0x14002799e  mov     [rbp+var_18], rsi
0x1400279a2  mov     [rbp+var_20], rsi
0x1400279a6  bt      r8d, 1Ch
0x1400279ab  jb      short loc_1400279F8
0x1400279ad  mov     ebx, 0C000000Dh
0x1400279b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400279b9  lea     rax, WPP_GLOBAL_Control
0x1400279c0  cmp     rcx, rax
0x1400279c3  jz      loc_140027DE0
0x1400279c9  mov     eax, [rcx+2Ch]
0x1400279cc  test    al, 1
0x1400279ce  jz      loc_140027DE0
0x1400279d4  mov     dword ptr [rsp+70h+var_48], r8d
0x1400279d9  lea     edx, [rsi+14h]
0x1400279dc  mov     [rsp+70h+var_50], 0C000000Dh
0x1400279e4  mov     r9d, 71Dh
0x1400279ea  mov     rcx, [rcx+18h]
0x1400279ee  call    WPP_SF_dDD
0x1400279f3  jmp     loc_140027DE0
0x1400279f8  lea     rax, [rbp+var_10]
0x1400279fc  mov     r9d, 0Ch
0x140027a02  mov     [rsp+70h+var_28], rax
0x140027a07  mov     r8, rdi
0x140027a0a  lea     rax, [rbp+var_20]
0x140027a0e  mov     [rsp+70h+var_30], rax
0x140027a13  lea     rax, [rbp+var_18]
0x140027a17  mov     [rsp+70h+var_38], rax
0x140027a1c  lea     rax, [rbp+arg_10]
0x140027a20  mov     [rsp+70h+Size], rax
0x140027a25  lea     rax, [rbp+arg_8]
0x140027a29  mov     [rsp+70h+var_48], rax
0x140027a2e  mov     byte ptr [rsp+70h+var_50], 5
0x140027a33  call    GetNodeInfoAndValidate
0x140027a38  mov     ebx, eax
0x140027a3a  test    eax, eax
0x140027a3c  jns     short loc_140027A85
0x140027a3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140027a45  lea     rax, WPP_GLOBAL_Control
0x140027a4c  cmp     rcx, rax
0x140027a4f  jz      loc_140027DE0
0x140027a55  mov     edx, [rcx+2Ch]
0x140027a58  test    dl, 1
0x140027a5b  jz      loc_140027DE0
0x140027a61  mov     edx, 15h
0x140027a66  mov     r9d, 72Dh
0x140027a6c  mov     rcx, [rcx+18h]
0x140027a70  lea     r8, WPP_a7e72e311a673739a589ba7821720449_Traceguids
0x140027a77  mov     [rsp+70h+var_50], ebx
0x140027a7b  call    WPP_SF_dd
0x140027a80  jmp     loc_140027DE0
0x140027a85  mov     edx, [rdi+20h]
0x140027a88  mov     ecx, 0FFFF0000h
0x140027a8d  test    ecx, edx
0x140027a8f  jnz     loc_140027DAD
0x140027a95  test    [rdi+2Ch], ecx
0x140027a98  jnz     loc_140027DAD
0x140027a9e  mov     r9b, byte ptr [rbp+arg_8]; int
0x140027aa2  movzx   eax, dx
0x140027aa5  movzx   eax, word ptr [rdi+2Ch]
0x140027aa9  mov     [rbp+arg_1A], ax
0x140027aad  mov     rax, [rbp+var_10]
0x140027ab1  mov     [rbp+arg_18], dx
0x140027ab5  mov     ecx, [rax+30h]
0x140027ab8  test    cl, 1
0x140027abb  jnz     loc_140027B8C
0x140027ac1  mov     rax, [rbp+var_20]
0x140027ac5  mov     r8d, 0C00h; int
0x140027acb  mov     [rsp+70h+var_30], rax; __int64
0x140027ad0  mov     dl, 1; int
0x140027ad2  mov     rax, [rbp+var_18]
0x140027ad6  mov     cl, 21h ; '!'; int
0x140027ad8  mov     [rsp+70h+var_38], rax; __int64
0x140027add  lea     rax, [rbp+arg_18]
0x140027ae1  mov     dword ptr [rsp+70h+Size], 4; Size
0x140027ae9  mov     [rsp+70h+var_48], rax; void *
0x140027aee  mov     al, byte ptr [rbp+arg_10]
0x140027af1  mov     byte ptr [rsp+70h+var_50], al; int
0x140027af5  call    SubmitControlRequest
0x140027afa  mov     ebx, eax
0x140027afc  test    eax, eax
0x140027afe  jns     short loc_140027B48
0x140027b00  mov     rcx, cs:WPP_GLOBAL_Control
0x140027b07  lea     rax, WPP_GLOBAL_Control
0x140027b0e  cmp     rcx, rax
0x140027b11  jz      loc_140027DE0
0x140027b17  mov     eax, [rcx+2Ch]
0x140027b1a  test    al, 1
0x140027b1c  jz      loc_140027DE0
0x140027b22  movzx   eax, [rbp+arg_1A]
0x140027b26  mov     edx, 17h
0x140027b2b  movzx   r8d, [rbp+arg_18]
0x140027b30  mov     r9d, 751h
0x140027b36  mov     dword ptr [rsp+70h+Size], ebx
0x140027b3a  mov     dword ptr [rsp+70h+var_48], eax
0x140027b3e  mov     [rsp+70h+var_50], r8d
0x140027b43  jmp     loc_140027DA2
0x140027b48  mov     rcx, cs:WPP_GLOBAL_Control
0x140027b4f  lea     rax, WPP_GLOBAL_Control
0x140027b56  cmp     rcx, rax
0x140027b59  jz      loc_140027DE0
0x140027b5f  mov     eax, [rcx+2Ch]
0x140027b62  test    al, 8
0x140027b64  jz      loc_140027DE0
0x140027b6a  movzx   eax, [rbp+arg_1A]
0x140027b6e  mov     edx, 18h
0x140027b73  movzx   r8d, [rbp+arg_18]
0x140027b78  mov     r9d, 755h
0x140027b7e  mov     dword ptr [rsp+70h+var_48], eax
0x140027b82  mov     [rsp+70h+var_50], r8d
0x140027b87  jmp     loc_1400279EA
0x140027b8c  mov     rsi, [rbp+var_20]
0x140027b90  lea     rax, [rbp+arg_0]
0x140027b94  mov     r14, [rbp+var_18]
0x140027b98  mov     r8d, 0D00h; int
0x140027b9e  mov     r15b, byte ptr [rbp+arg_10]
0x140027ba2  mov     dl, 81h; int
0x140027ba4  mov     [rsp+70h+var_30], rsi; __int64
0x140027ba9  mov     cl, 0A1h; int
0x140027bab  mov     [rsp+70h+var_38], r14; __int64
0x140027bb0  mov     dword ptr [rsp+70h+Size], 1; Size
0x140027bb8  mov     [rsp+70h+var_48], rax; void *
0x140027bbd  mov     byte ptr [rsp+70h+var_50], r15b; int
0x140027bc2  call    SubmitControlRequest
0x140027bc7  xor     ecx, ecx
0x140027bc9  mov     ebx, eax
0x140027bcb  test    eax, eax
0x140027bcd  jns     short loc_140027C01
0x140027bcf  mov     rcx, cs:WPP_GLOBAL_Control
0x140027bd6  lea     rax, WPP_GLOBAL_Control
0x140027bdd  cmp     rcx, rax
0x140027be0  jz      loc_140027DE0
0x140027be6  mov     eax, [rcx+2Ch]
0x140027be9  test    al, 1
0x140027beb  jz      loc_140027DE0
0x140027bf1  mov     edx, 19h
0x140027bf6  mov     r9d, 766h
0x140027bfc  jmp     loc_140027A6C
0x140027c01  mov     eax, [rdi+24h]
0x140027c04  test    al, 2
0x140027c06  jz      loc_140027CEE
0x140027c0c  cmp     [rbp+arg_0], cl
0x140027c0f  jz      short loc_140027C7F
0x140027c11  mov     r9b, byte ptr [rbp+arg_8]; int
0x140027c15  lea     rax, [rbp+arg_0]
0x140027c19  mov     [rsp+70h+var_30], rsi; __int64
0x140027c1e  mov     r8d, 0D00h; int
0x140027c24  mov     [rsp+70h+var_38], r14; __int64
0x140027c29  mov     dl, 1; int
0x140027c2b  mov     dword ptr [rsp+70h+Size], 1; Size
0x140027c33  mov     [rbp+arg_0], cl
0x140027c36  mov     cl, 21h ; '!'; int
0x140027c38  mov     [rsp+70h+var_48], rax; void *
0x140027c3d  mov     byte ptr [rsp+70h+var_50], r15b; int
0x140027c42  call    SubmitControlRequest
0x140027c47  mov     ebx, eax
0x140027c49  test    eax, eax
0x140027c4b  jns     short loc_140027C7F
0x140027c4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140027c54  lea     rax, WPP_GLOBAL_Control
0x140027c5b  cmp     rcx, rax
0x140027c5e  jz      loc_140027DE0
0x140027c64  mov     eax, [rcx+2Ch]
0x140027c67  test    al, 1
0x140027c69  jz      loc_140027DE0
0x140027c6f  mov     edx, 1Ah
0x140027c74  mov     r9d, 77Eh
0x140027c7a  jmp     loc_140027A6C
0x140027c7f  mov     r9b, byte ptr [rbp+arg_8]; int
0x140027c83  lea     rax, [rbp+arg_18]
0x140027c87  mov     [rsp+70h+var_30], rsi; __int64
0x140027c8c  mov     r8d, 0C00h; int
0x140027c92  mov     [rsp+70h+var_38], r14; __int64
0x140027c97  mov     dl, 1; int
0x140027c99  mov     dword ptr [rsp+70h+Size], 4; Size
0x140027ca1  mov     cl, 21h ; '!'; int
0x140027ca3  mov     [rsp+70h+var_48], rax; void *
0x140027ca8  mov     byte ptr [rsp+70h+var_50], r15b; int
0x140027cad  call    SubmitControlRequest
0x140027cb2  mov     ebx, eax
0x140027cb4  test    eax, eax
0x140027cb6  jns     loc_140027D62
0x140027cbc  mov     rcx, cs:WPP_GLOBAL_Control
0x140027cc3  lea     rax, WPP_GLOBAL_Control
0x140027cca  cmp     rcx, rax
0x140027ccd  jz      loc_140027DE0
0x140027cd3  mov     eax, [rcx+2Ch]
0x140027cd6  test    al, 1
0x140027cd8  jz      loc_140027DE0
0x140027cde  mov     edx, 1Bh
0x140027ce3  mov     r9d, 78Eh
0x140027ce9  jmp     loc_140027A6C
0x140027cee  cmp     [rbp+arg_0], cl
0x140027cf1  jnz     short loc_140027D62
0x140027cf3  mov     r9b, byte ptr [rbp+arg_8]; int
0x140027cf7  lea     rax, [rbp+arg_0]
0x140027cfb  mov     [rsp+70h+var_30], rsi; __int64
0x140027d00  mov     r8d, 0D00h; int
0x140027d06  mov     [rsp+70h+var_38], r14; __int64
0x140027d0b  mov     dl, 1; int
0x140027d0d  mov     dword ptr [rsp+70h+Size], 1; Size
0x140027d15  mov     cl, 21h ; '!'; int
0x140027d17  mov     [rsp+70h+var_48], rax; void *
0x140027d1c  mov     byte ptr [rsp+70h+var_50], r15b; int
0x140027d21  mov     [rbp+arg_0], 1
0x140027d25  call    SubmitControlRequest
0x140027d2a  mov     ebx, eax
0x140027d2c  test    eax, eax
0x140027d2e  jns     short loc_140027D62
0x140027d30  mov     rcx, cs:WPP_GLOBAL_Control
0x140027d37  lea     rax, WPP_GLOBAL_Control
0x140027d3e  cmp     rcx, rax
0x140027d41  jz      loc_140027DE0
0x140027d47  mov     eax, [rcx+2Ch]
0x140027d4a  test    al, 1
0x140027d4c  jz      loc_140027DE0
0x140027d52  mov     edx, 1Ch
0x140027d57  mov     r9d, 7A5h
0x140027d5d  jmp     loc_140027A6C
0x140027d62  mov     rcx, cs:WPP_GLOBAL_Control
0x140027d69  lea     rax, WPP_GLOBAL_Control
0x140027d70  cmp     rcx, rax
0x140027d73  jz      short loc_140027DE0
0x140027d75  mov     eax, [rcx+2Ch]
0x140027d78  test    al, 8
0x140027d7a  jz      short loc_140027DE0
0x140027d7c  movzx   r9d, [rbp+arg_18]
0x140027d81  mov     edx, 1Dh
0x140027d86  movzx   r8d, [rbp+arg_1A]
0x140027d8b  mov     eax, [rdi+24h]
0x140027d8e  mov     dword ptr [rsp+70h+Size], eax
0x140027d92  mov     dword ptr [rsp+70h+var_48], r8d
0x140027d97  mov     [rsp+70h+var_50], r9d
0x140027d9c  mov     r9d, 7ABh
0x140027da2  mov     rcx, [rcx+18h]
0x140027da6  call    WPP_SF_dDDD
0x140027dab  jmp     short loc_140027DE0
0x140027dad  mov     ebx, 0C000000Dh
0x140027db2  mov     rcx, cs:WPP_GLOBAL_Control
0x140027db9  lea     rax, WPP_GLOBAL_Control
0x140027dc0  cmp     rcx, rax
0x140027dc3  jz      short loc_140027DE0
0x140027dc5  mov     eax, [rcx+2Ch]
0x140027dc8  test    al, 1
0x140027dca  jz      short loc_140027DE0
0x140027dcc  mov     eax, [rdi+2Ch]
0x140027dcf  mov     rcx, [rcx+18h]
0x140027dd3  mov     dword ptr [rsp+70h+Size], eax
0x140027dd7  mov     dword ptr [rsp+70h+var_48], edx
0x140027ddb  call    WPP_SF_dDdd
0x140027de0  mov     [r13+30h], ebx
0x140027de4  mov     eax, ebx
0x140027de6  add     rsp, 70h
0x140027dea  pop     r15
0x140027dec  pop     r14
0x140027dee  pop     r13
0x140027df0  pop     rdi
0x140027df1  pop     rsi
0x140027df2  pop     rbx
0x140027df3  pop     rbp
0x140027df4  retn
```
