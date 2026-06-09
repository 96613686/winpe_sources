# ExtensionUnitSetHandler

- ea: `0x140007bb0`
- end: `0x140007e68`
- name: `ExtensionUnitSetHandler`
- size: `696`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140004bac`
- `0x140007bb0`
- `0x140008640`
- `0x140008f80`
- `0x1400091c4`
- `0x140009934`
- `0x14001b118`

## pseudocode

```c
__int64 __fastcall ExtensionUnitSetHandler(PIRP Irp, __int64 a2, __int64 a3)
{
  unsigned __int16 v6; // r14
  int NodeInfoAndValidate; // eax
  unsigned int v8; // ebx
  __int64 v9; // r15
  __int64 v10; // r12
  char v11; // r13
  unsigned __int16 v12; // r14
  int v13; // edx
  int v14; // r8d
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  char v19; // [rsp+20h] [rbp-50h]
  int v20; // [rsp+20h] [rbp-50h]
  size_t Size; // [rsp+30h] [rbp-40h]
  unsigned __int8 v22[8]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v23; // [rsp+58h] [rbp-18h] BYREF
  __int64 v24; // [rsp+60h] [rbp-10h] BYREF
  _BYTE v25[8]; // [rsp+68h] [rbp-8h] BYREF
  int v26; // [rsp+B0h] [rbp+40h] BYREF
  int v27; // [rsp+C8h] [rbp+58h] BYREF

  LOBYTE(v26) = 0;
  LOBYTE(v27) = 0;
  *(_WORD *)v22 = 0;
  v24 = 0;
  v23 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_d4a62a8645b530c86adbc368ec44f47c_Traceguids);
  if ( (Irp->Tail.Overlay.CurrentStackLocation->Control & 1) != 0 )
  {
    v6 = *(_WORD *)(a2 + 16);
    v19 = 9;
    NodeInfoAndValidate = GetNodeInfoAndValidate(Irp, a2, a3, v6, v19, &v26, &v27, &v24, &v23, v25);
    v8 = NodeInfoAndValidate;
    if ( NodeInfoAndValidate < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
        goto LABEL_9;
      v17 = 15;
    }
    else
    {
      v9 = v23;
      v10 = v24;
      v11 = v27;
      LODWORD(Size) = 2;
      v12 = v6 << 8;
      LOBYTE(v20) = v27;
      NodeInfoAndValidate = SubmitControlRequest(0xA1u, 0x85u, v12, v26, v20, v22, Size, v24, v23);
      v8 = NodeInfoAndValidate;
      if ( NodeInfoAndValidate >= 0 )
      {
        if ( Irp->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length < *(unsigned __int16 *)v22 )
        {
          v8 = -1073741789;
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            v17 = 17;
            v18 = 3221225507LL;
            goto LABEL_20;
          }
        }
        else
        {
          NodeInfoAndValidate = SubmitControlRequestA(
                                  (_DWORD)Irp,
                                  v13,
                                  v14,
                                  v12,
                                  v26,
                                  v11,
                                  a3,
                                  *(unsigned __int16 *)v22,
                                  v10,
                                  v9);
          v8 = NodeInfoAndValidate;
          if ( NodeInfoAndValidate < 0 )
          {
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              v17 = 18;
              goto LABEL_19;
            }
          }
        }
LABEL_9:
        Irp->IoStatus.Status = v8;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_d4a62a8645b530c86adbc368ec44f47c_Traceguids, v8);
        return v8;
      }
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
        goto LABEL_9;
      v17 = 16;
    }
LABEL_19:
    v18 = (unsigned int)NodeInfoAndValidate;
LABEL_20:
    WPP_SF_d(v16->AttachedDevice, v17, WPP_d4a62a8645b530c86adbc368ec44f47c_Traceguids, v18);
    goto LABEL_9;
  }
  v8 = QueuePropertyRequest(Irp);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_d4a62a8645b530c86adbc368ec44f47c_Traceguids);
  return v8;
}

```

## disassembly

```asm
0x140007bb0  mov     [rsp-38h+arg_8], rbx
0x140007bb5  push    rbp
0x140007bb6  push    rsi
0x140007bb7  push    rdi
0x140007bb8  push    r12
0x140007bba  push    r13
0x140007bbc  push    r14
0x140007bbe  push    r15
0x140007bc0  mov     rbp, rsp
0x140007bc3  sub     rsp, 70h
0x140007bc7  xor     r15d, r15d
0x140007bca  mov     rsi, r8
0x140007bcd  mov     byte ptr [rbp+arg_0], r15b
0x140007bd1  mov     rbx, rdx
0x140007bd4  mov     byte ptr [rbp+arg_18], r15b
0x140007bd8  mov     rdi, rcx
0x140007bdb  mov     word ptr [rbp+var_20], r15w
0x140007be0  mov     [rbp+var_10], r15
0x140007be4  mov     [rbp+var_18], r15
0x140007be8  mov     rcx, cs:WPP_GLOBAL_Control
0x140007bef  lea     r14, WPP_GLOBAL_Control
0x140007bf6  cmp     rcx, r14
0x140007bf9  jz      short loc_140007C05
0x140007bfb  cmp     byte ptr [rcx+29h], 5
0x140007bff  jnb     loc_140007DAE
0x140007c05  mov     rax, [rdi+0B8h]
0x140007c0c  mov     r8, rsi
0x140007c0f  mov     rdx, rbx
0x140007c12  mov     rcx, rdi; Irp
0x140007c15  test    byte ptr [rax+3], 1
0x140007c19  jz      loc_140007D34
0x140007c1f  movzx   r14d, word ptr [rbx+10h]
0x140007c24  lea     rax, [rbp+var_8]
0x140007c28  mov     [rsp+70h+var_28], rax
0x140007c2d  movzx   r9d, r14w
0x140007c31  lea     rax, [rbp+var_18]
0x140007c35  mov     [rsp+70h+var_30], rax
0x140007c3a  lea     rax, [rbp+var_10]
0x140007c3e  mov     [rsp+70h+var_38], rax
0x140007c43  lea     rax, [rbp+arg_18]
0x140007c47  mov     [rsp+70h+Size], rax
0x140007c4c  lea     rax, [rbp+arg_0]
0x140007c50  mov     [rsp+70h+var_48], rax
0x140007c55  mov     byte ptr [rsp+70h+var_50], 9
0x140007c5a  call    GetNodeInfoAndValidate
0x140007c5f  mov     ebx, eax
0x140007c61  test    eax, eax
0x140007c63  js      loc_140007D86
0x140007c69  mov     r15, [rbp+var_18]
0x140007c6d  lea     rax, [rbp+var_20]
0x140007c71  mov     r12, [rbp+var_10]
0x140007c75  mov     dl, 85h; int
0x140007c77  mov     r13b, byte ptr [rbp+arg_18]
0x140007c7b  mov     cl, 0A1h; int
0x140007c7d  mov     r9b, byte ptr [rbp+arg_0]; int
0x140007c81  mov     [rsp+70h+var_30], r15; __int64
0x140007c86  mov     [rsp+70h+var_38], r12; __int64
0x140007c8b  mov     dword ptr [rsp+70h+Size], 2; Size
0x140007c93  mov     [rsp+70h+var_48], rax; void *
0x140007c98  shl     r14w, 8
0x140007c9d  movzx   r8d, r14w; int
0x140007ca1  mov     byte ptr [rsp+70h+var_50], r13b; int
0x140007ca6  call    SubmitControlRequest
0x140007cab  mov     ebx, eax
0x140007cad  test    eax, eax
0x140007caf  js      loc_140007DF2
0x140007cb5  mov     rax, [rdi+0B8h]
0x140007cbc  movzx   ecx, word ptr [rbp+var_20]
0x140007cc0  cmp     [rax+8], ecx
0x140007cc3  jb      loc_140007E1A
0x140007cc9  mov     al, byte ptr [rbp+arg_0]
0x140007ccc  movzx   r9d, r14w
0x140007cd0  mov     [rsp+70h+var_28], r15
0x140007cd5  mov     [rsp+70h+var_30], r12
0x140007cda  mov     dword ptr [rsp+70h+var_38], ecx
0x140007cde  mov     rcx, rdi
0x140007ce1  mov     [rsp+70h+Size], rsi
0x140007ce6  mov     byte ptr [rsp+70h+var_48], r13b
0x140007ceb  mov     byte ptr [rsp+70h+var_50], al
0x140007cef  call    SubmitControlRequestA
0x140007cf4  mov     ebx, eax
0x140007cf6  test    eax, eax
0x140007cf8  js      loc_140007E42
0x140007cfe  lea     rsi, WPP_GLOBAL_Control
0x140007d05  mov     [rdi+30h], ebx
0x140007d08  mov     rcx, cs:WPP_GLOBAL_Control
0x140007d0f  cmp     rcx, rsi
0x140007d12  jz      short loc_140007D4E
0x140007d14  cmp     byte ptr [rcx+29h], 5
0x140007d18  jb      short loc_140007D4E
0x140007d1a  mov     rcx, [rcx+18h]
0x140007d1e  lea     r8, WPP_d4a62a8645b530c86adbc368ec44f47c_Traceguids
0x140007d25  mov     edx, 13h
0x140007d2a  mov     r9d, ebx
0x140007d2d  call    WPP_SF_d
0x140007d32  jmp     short loc_140007D4E
0x140007d34  lea     r9, ExtensionUnitSetHandler
0x140007d3b  call    QueuePropertyRequest
0x140007d40  mov     ebx, eax
0x140007d42  mov     rcx, cs:WPP_GLOBAL_Control
0x140007d49  cmp     rcx, r14
0x140007d4c  jnz     short loc_140007D69
0x140007d4e  mov     eax, ebx
0x140007d50  mov     rbx, [rsp+70h+arg_8]
0x140007d58  add     rsp, 70h
0x140007d5c  pop     r15
0x140007d5e  pop     r14
0x140007d60  pop     r13
0x140007d62  pop     r12
0x140007d64  pop     rdi
0x140007d65  pop     rsi
0x140007d66  pop     rbp
0x140007d67  retn
0x140007d69  cmp     byte ptr [rcx+29h], 5
0x140007d6d  jb      short loc_140007D4E
0x140007d6f  mov     rcx, [rcx+18h]
0x140007d73  lea     r8, WPP_d4a62a8645b530c86adbc368ec44f47c_Traceguids
0x140007d7a  mov     edx, 0Eh
0x140007d7f  call    WPP_SF_
0x140007d84  jmp     short loc_140007D4E
0x140007d86  mov     rcx, cs:WPP_GLOBAL_Control
0x140007d8d  lea     rsi, WPP_GLOBAL_Control
0x140007d94  cmp     rcx, rsi
0x140007d97  jz      loc_140007D05
0x140007d9d  cmp     byte ptr [rcx+29h], 5
0x140007da1  jb      loc_140007D05
0x140007da7  mov     edx, 0Fh
0x140007dac  jmp     short loc_140007DCD
0x140007dae  mov     rcx, [rcx+18h]
0x140007db2  lea     r8, WPP_d4a62a8645b530c86adbc368ec44f47c_Traceguids
0x140007db9  mov     edx, 0Dh
0x140007dbe  call    WPP_SF_
0x140007dc3  jmp     loc_140007C05
0x140007dc8  mov     edx, 12h
0x140007dcd  mov     r9d, eax
0x140007dd0  jmp     short loc_140007DDD
0x140007dd2  mov     edx, 11h
0x140007dd7  mov     r9d, 0C0000023h
0x140007ddd  mov     rcx, [rcx+18h]
0x140007de1  lea     r8, WPP_d4a62a8645b530c86adbc368ec44f47c_Traceguids
0x140007de8  call    WPP_SF_d
0x140007ded  jmp     loc_140007D05
0x140007df2  mov     rcx, cs:WPP_GLOBAL_Control
0x140007df9  lea     rsi, WPP_GLOBAL_Control
0x140007e00  cmp     rcx, rsi
0x140007e03  jz      loc_140007D05
0x140007e09  cmp     byte ptr [rcx+29h], 5
0x140007e0d  jb      loc_140007D05
0x140007e13  mov     edx, 10h
0x140007e18  jmp     short loc_140007DCD
0x140007e1a  mov     ebx, 0C0000023h
0x140007e1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140007e26  lea     rsi, WPP_GLOBAL_Control
0x140007e2d  cmp     rcx, rsi
0x140007e30  jz      loc_140007D05
0x140007e36  cmp     byte ptr [rcx+29h], 5
0x140007e3a  jb      loc_140007D05
0x140007e40  jmp     short loc_140007DD2
0x140007e42  mov     rcx, cs:WPP_GLOBAL_Control
0x140007e49  lea     rsi, WPP_GLOBAL_Control
0x140007e50  cmp     rcx, rsi
0x140007e53  jz      loc_140007D05
0x140007e59  cmp     byte ptr [rcx+29h], 5
0x140007e5d  jb      loc_140007D05
0x140007e63  jmp     loc_140007DC8
```
