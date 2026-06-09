# OncRpcSeProcessIncomingGssReplyMessage

- ea: `0x140009dc4`
- end: `0x14000a184`
- name: `OncRpcSeProcessIncomingGssReplyMessage`
- size: `960`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140002f50`

## callees

- `0x140001de4`
- `0x140001e90`
- `0x1400020c0`
- `0x140009dc4`
- `0x14000a18c`
- `0x14000a814`
- `0x14000bf88`
- `0x14000cb78`
- `0x14000d104`

## pseudocode

```c
__int64 __fastcall OncRpcSeProcessIncomingGssReplyMessage(__int64 a1, _DWORD *a2, __int64 a3)
{
  __int64 v4; // rcx
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // r8d
  int v10; // eax
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  int v17; // ecx
  unsigned int v18; // eax
  __int64 v19; // rbp
  unsigned int v20; // r13d
  void *v21; // rbp
  __int64 v22; // r9
  __int64 PtrFromPtrAndOffset; // rax
  __int64 v24; // r9
  unsigned int *v25; // r15
  __int64 v26; // r14
  unsigned int v27; // r15d
  unsigned int v28; // eax
  __int64 v29; // rbx
  unsigned int v30; // ebp
  void *v31; // rbx
  __int64 v32; // [rsp+A0h] [rbp+18h] BYREF

  v32 = a3;
  v4 = *(_QWORD *)(a1 + 1032);
  if ( v4 && *(_QWORD *)(v4 + 1008) )
  {
    v6 = 0;
    OncRpcSeReferenceOutboundGssCtx(*(_QWORD *)(v4 + 1008));
    v7 = *(_QWORD *)(a1 + 1032);
    v8 = *(_QWORD *)(v7 + 1008);
    *(_QWORD *)(a1 + 1008) = v8;
    if ( !*(_DWORD *)(a1 + 272) && !*(_DWORD *)(a1 + 640) && *(_DWORD *)(v7 + 276) == 100003 )
    {
      v9 = *(_DWORD *)(v7 + 312);
      if ( (unsigned int)(v9 - 1) <= 1 && !*(_DWORD *)(v7 + 284) && v8 )
      {
        v10 = OncRpcSepProcessIncomingReplyGssInit(a1, (__int64)a2);
        v6 = v10;
        if ( v10 >= 0 )
          goto LABEL_14;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
            goto LABEL_14;
          v12 = 56;
          v13 = (unsigned int)v10;
          goto LABEL_13;
        }
        return (unsigned int)v6;
      }
      if ( !v9 && *(_DWORD *)(a1 + 288) == 6 && v8 && *(_DWORD *)(v8 + 64) == 2 )
      {
        LODWORD(v32) = _byteswap_ulong(*(_DWORD *)(v7 + 316));
        v6 = OncRpcSepVerifyMessage(
               (struct _SecHandle *)(v8 + 96),
               a2,
               0,
               &v32,
               4u,
               a1 + 32,
               *(_QWORD *)(a1 + 360),
               *(_DWORD *)(a1 + 352));
        if ( v6 >= 0 )
        {
          v17 = *(_DWORD *)(*(_QWORD *)(a1 + 1008) + 120LL);
          if ( v17 == 2 )
          {
            v18 = XdrDecodeInt_0(a1);
            v19 = *(_QWORD *)(a1 + 72);
            v20 = v18;
            if ( v19 )
              v21 = *(void **)(v19 + 64);
            else
              v21 = 0;
            LODWORD(v32) = XdrDecodeInt_0(a1);
            LOBYTE(v22) = 1;
            PtrFromPtrAndOffset = OncRpcBufMgrpContextGetPtrFromPtrAndOffset(a1 + 32, v21, (v20 + 3) & 0xFFFFFFFC, v22);
            v25 = (unsigned int *)PtrFromPtrAndOffset;
            if ( !PtrFromPtrAndOffset )
              goto LABEL_31;
            LOBYTE(v24) = 1;
            v26 = OncRpcBufMgrpContextGetPtrFromPtrAndOffset(a1 + 32, PtrFromPtrAndOffset, 4, v24);
            if ( !v26 )
              goto LABEL_31;
            v27 = _byteswap_ulong(*v25);
            if ( (_DWORD)v32 != *(_DWORD *)(*(_QWORD *)(a1 + 1032) + 316LL) )
              v6 = -1073741790;
            if ( (unsigned int)OncRpcBufMgrpContextGetValidDataLengthFromPtr(a1 + 32, v21) >= v20
              && (unsigned int)OncRpcBufMgrpContextGetValidDataLengthFromPtr(a1 + 32, v26) >= v27 )
            {
              if ( v6 >= 0 )
              {
                v6 = OncRpcSepVerifyMessage(
                       (struct _SecHandle *)(*(_QWORD *)(a1 + 1008) + 96LL),
                       a2,
                       a1 + 32,
                       v21,
                       v20,
                       a1 + 32,
                       v26,
                       v27);
                if ( v6 < 0 )
                {
                  v11 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    return (unsigned int)v6;
                  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                  {
                    v12 = 58;
                    v13 = (unsigned int)v6;
LABEL_13:
                    WPP_SF_d(v11->AttachedDevice, v12, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, v13);
                  }
                }
              }
            }
            else
            {
LABEL_31:
              v6 = -2147483643;
            }
          }
          else
          {
            if ( v17 != 3 )
              goto LABEL_14;
            v28 = XdrDecodeInt_0(a1);
            v29 = *(_QWORD *)(a1 + 72);
            v30 = v28;
            if ( v29 )
              v31 = *(void **)(v29 + 64);
            else
              v31 = 0;
            if ( (unsigned int)OncRpcBufMgrpContextGetValidDataLengthFromPtr(a1 + 32, v31) < v28 )
            {
              v6 = -2147483643;
              goto LABEL_14;
            }
            v6 = OncRpcSepDecryptMessage(*(_QWORD *)(a1 + 1008) + 96LL, a2, a1 + 32, v31, v30);
            if ( v6 >= 0 )
            {
              if ( (unsigned int)XdrDecodeInt_0(a1) != *(_DWORD *)(*(_QWORD *)(a1 + 1032) + 316LL) )
                v6 = -1073741790;
              goto LABEL_14;
            }
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
            {
              v16 = 59;
              goto LABEL_52;
            }
          }
        }
        else
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
          {
            v16 = 57;
LABEL_52:
            WPP_SF_d(v15->AttachedDevice, v16, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, (unsigned int)v6);
          }
        }
      }
    }
LABEL_14:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        60,
        WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids,
        (unsigned int)v6);
    return (unsigned int)v6;
  }
  return 0;
}

```

## disassembly

```asm
0x140009dc4  mov     [rsp+arg_10], r8
0x140009dc9  push    rbx
0x140009dca  push    rbp
0x140009dcb  push    rsi
0x140009dcc  push    rdi
0x140009dcd  push    r12
0x140009dcf  push    r13
0x140009dd1  push    r14
0x140009dd3  push    r15
0x140009dd5  sub     rsp, 48h
0x140009dd9  mov     rdi, rcx
0x140009ddc  xor     r14d, r14d
0x140009ddf  mov     rcx, [rcx+408h]
0x140009de6  mov     r12, rdx
0x140009de9  test    rcx, rcx
0x140009dec  jz      loc_14000A170
0x140009df2  cmp     [rcx+3F0h], r14
0x140009df9  jz      loc_14000A170
0x140009dff  mov     rcx, [rcx+3F0h]
0x140009e06  mov     ebx, r14d
0x140009e09  call    OncRpcSeReferenceOutboundGssCtx
0x140009e0e  lea     r15, WPP_GLOBAL_Control
0x140009e15  mov     rdx, [rdi+408h]
0x140009e1c  mov     rcx, [rdx+3F0h]
0x140009e23  mov     [rdi+3F0h], rcx
0x140009e2a  cmp     [rdi+110h], r14d
0x140009e31  jnz     loc_140009EBC
0x140009e37  cmp     [rdi+280h], r14d
0x140009e3e  jnz     short loc_140009EBC
0x140009e40  cmp     dword ptr [rdx+114h], 186A3h
0x140009e4a  jnz     short loc_140009EBC
0x140009e4c  mov     r8d, [rdx+138h]
0x140009e53  lea     eax, [r8-1]
0x140009e57  cmp     eax, 1
0x140009e5a  ja      loc_140009EEE
0x140009e60  cmp     [rdx+11Ch], r14d
0x140009e67  jnz     loc_140009EEE
0x140009e6d  test    rcx, rcx
0x140009e70  jz      short loc_140009EEE
0x140009e72  mov     rdx, r12
0x140009e75  mov     rcx, rdi
0x140009e78  call    OncRpcSepProcessIncomingReplyGssInit
0x140009e7d  mov     ebx, eax
0x140009e7f  test    eax, eax
0x140009e81  jns     short loc_140009EBC
0x140009e83  mov     rcx, cs:WPP_GLOBAL_Control
0x140009e8a  lea     rdx, WPP_GLOBAL_Control
0x140009e91  cmp     rcx, rdx
0x140009e94  jz      short loc_140009EE7
0x140009e96  mov     edx, [rcx+2Ch]
0x140009e99  test    dl, 40h
0x140009e9c  jz      short loc_140009EB5
0x140009e9e  lea     edx, [r14+38h]
0x140009ea2  mov     r9d, eax
0x140009ea5  mov     rcx, [rcx+18h]
0x140009ea9  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x140009eb0  call    WPP_SF_d
0x140009eb5  lea     r15, WPP_GLOBAL_Control
0x140009ebc  mov     rcx, cs:WPP_GLOBAL_Control
0x140009ec3  cmp     rcx, r15
0x140009ec6  jz      short loc_140009EE7
0x140009ec8  mov     eax, [rcx+2Ch]
0x140009ecb  test    al, 1
0x140009ecd  jz      short loc_140009EE7
0x140009ecf  mov     rcx, [rcx+18h]
0x140009ed3  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x140009eda  mov     edx, 3Ch ; '<'
0x140009edf  mov     r9d, ebx
0x140009ee2  call    WPP_SF_d
0x140009ee7  mov     eax, ebx
0x140009ee9  jmp     loc_14000A172
0x140009eee  test    r8d, r8d
0x140009ef1  jnz     short loc_140009EBC
0x140009ef3  cmp     dword ptr [rdi+120h], 6
0x140009efa  jnz     short loc_140009EBC
0x140009efc  test    rcx, rcx
0x140009eff  jz      short loc_140009EBC
0x140009f01  cmp     dword ptr [rcx+40h], 2
0x140009f05  jnz     short loc_140009EBC
0x140009f07  mov     eax, [rdx+13Ch]
0x140009f0d  lea     rsi, [rdi+20h]
0x140009f11  bswap   eax
0x140009f13  mov     dword ptr [rsp+88h+arg_10], eax
0x140009f1a  lea     r9, [rsp+88h+arg_10]
0x140009f22  mov     eax, [rdi+160h]
0x140009f28  add     rcx, 60h ; '`'
0x140009f2c  mov     [rsp+88h+var_50], eax
0x140009f30  xor     r8d, r8d
0x140009f33  mov     rax, [rdi+168h]
0x140009f3a  mov     rdx, r12
0x140009f3d  mov     [rsp+88h+var_58], rax
0x140009f42  mov     [rsp+88h+var_60], rsi
0x140009f47  mov     [rsp+88h+var_68], 4
0x140009f4f  call    OncRpcSepVerifyMessage
0x140009f54  mov     ebx, eax
0x140009f56  test    eax, eax
0x140009f58  jns     short loc_140009F7F
0x140009f5a  mov     rcx, cs:WPP_GLOBAL_Control
0x140009f61  cmp     rcx, r15
0x140009f64  jz      loc_140009EBC
0x140009f6a  mov     eax, [rcx+2Ch]
0x140009f6d  test    al, 40h
0x140009f6f  jz      loc_140009EBC
0x140009f75  mov     edx, 39h ; '9'
0x140009f7a  jmp     loc_14000A133
0x140009f7f  mov     rax, [rdi+3F0h]
0x140009f86  mov     ecx, [rax+78h]
0x140009f89  cmp     ecx, 2
0x140009f8c  jnz     loc_14000A0B2
0x140009f92  mov     rcx, rdi
0x140009f95  call    XdrDecodeInt_0
0x140009f9a  mov     rbp, [rdi+48h]
0x140009f9e  mov     r13d, eax
0x140009fa1  test    rbp, rbp
0x140009fa4  jnz     short loc_140009FAB
0x140009fa6  mov     rbp, r14
0x140009fa9  jmp     short loc_140009FAF
0x140009fab  mov     rbp, [rbp+40h]
0x140009faf  mov     rcx, rdi
0x140009fb2  call    XdrDecodeInt_0
0x140009fb7  lea     r8d, [r13+3]
0x140009fbb  mov     dword ptr [rsp+88h+arg_10], eax
0x140009fc2  and     r8d, 0FFFFFFFCh
0x140009fc6  mov     r9b, 1
0x140009fc9  mov     rdx, rbp
0x140009fcc  mov     rcx, rsi
0x140009fcf  call    OncRpcBufMgrpContextGetPtrFromPtrAndOffset
0x140009fd4  mov     r15, rax
0x140009fd7  test    rax, rax
0x140009fda  jnz     short loc_140009FE6
0x140009fdc  mov     ebx, 80000005h
0x140009fe1  jmp     loc_140009EB5
0x140009fe6  mov     r9b, 1
0x140009fe9  mov     r8d, 4
0x140009fef  mov     rdx, r15
0x140009ff2  mov     rcx, rsi
0x140009ff5  call    OncRpcBufMgrpContextGetPtrFromPtrAndOffset
0x140009ffa  mov     r14, rax
0x140009ffd  test    rax, rax
0x14000a000  jz      short loc_140009FDC
0x14000a002  mov     rax, [rdi+408h]
0x14000a009  mov     ecx, 0C0000022h
0x14000a00e  mov     edx, dword ptr [rsp+88h+arg_10]
0x14000a015  mov     r15d, [r15]
0x14000a018  bswap   r15d
0x14000a01b  cmp     edx, [rax+13Ch]
0x14000a021  mov     rdx, rbp
0x14000a024  cmovnz  ebx, ecx
0x14000a027  mov     rcx, rsi
0x14000a02a  call    OncRpcBufMgrpContextGetValidDataLengthFromPtr
0x14000a02f  cmp     eax, r13d
0x14000a032  jb      short loc_140009FDC
0x14000a034  mov     rdx, r14
0x14000a037  mov     rcx, rsi
0x14000a03a  call    OncRpcBufMgrpContextGetValidDataLengthFromPtr
0x14000a03f  cmp     eax, r15d
0x14000a042  jb      short loc_140009FDC
0x14000a044  test    ebx, ebx
0x14000a046  js      loc_140009EB5
0x14000a04c  mov     rcx, [rdi+3F0h]
0x14000a053  mov     r9, rbp
0x14000a056  mov     [rsp+88h+var_50], r15d
0x14000a05b  add     rcx, 60h ; '`'
0x14000a05f  mov     [rsp+88h+var_58], r14
0x14000a064  mov     r8, rsi
0x14000a067  mov     [rsp+88h+var_60], rsi
0x14000a06c  mov     rdx, r12
0x14000a06f  mov     [rsp+88h+var_68], r13d
0x14000a074  call    OncRpcSepVerifyMessage
0x14000a079  mov     ebx, eax
0x14000a07b  test    eax, eax
0x14000a07d  jns     loc_140009EB5
0x14000a083  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a08a  lea     rax, WPP_GLOBAL_Control
0x14000a091  cmp     rcx, rax
0x14000a094  jz      loc_140009EE7
0x14000a09a  mov     eax, [rcx+2Ch]
0x14000a09d  test    al, 40h
0x14000a09f  jz      loc_140009EB5
0x14000a0a5  mov     edx, 3Ah ; ':'
0x14000a0aa  mov     r9d, ebx
0x14000a0ad  jmp     loc_140009EA5
0x14000a0b2  cmp     ecx, 3
0x14000a0b5  jnz     loc_140009EBC
0x14000a0bb  mov     rcx, rdi
0x14000a0be  call    XdrDecodeInt_0
0x14000a0c3  mov     rbx, [rdi+48h]
0x14000a0c7  mov     ebp, eax
0x14000a0c9  test    rbx, rbx
0x14000a0cc  jnz     short loc_14000A0D3
0x14000a0ce  mov     rbx, r14
0x14000a0d1  jmp     short loc_14000A0D7
0x14000a0d3  mov     rbx, [rbx+40h]
0x14000a0d7  mov     rdx, rbx
0x14000a0da  mov     rcx, rsi
0x14000a0dd  call    OncRpcBufMgrpContextGetValidDataLengthFromPtr
0x14000a0e2  cmp     eax, ebp
0x14000a0e4  jnb     short loc_14000A0F0
0x14000a0e6  mov     ebx, 80000005h
0x14000a0eb  jmp     loc_140009EBC
0x14000a0f0  mov     rcx, [rdi+3F0h]
0x14000a0f7  mov     r9, rbx
0x14000a0fa  add     rcx, 60h ; '`'
0x14000a0fe  mov     [rsp+88h+var_68], ebp
0x14000a102  mov     r8, rsi
0x14000a105  mov     rdx, r12
0x14000a108  call    OncRpcSepDecryptMessage
0x14000a10d  mov     ebx, eax
0x14000a10f  test    eax, eax
0x14000a111  jns     short loc_14000A14B
0x14000a113  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a11a  cmp     rcx, r15
0x14000a11d  jz      loc_140009EBC
0x14000a123  mov     eax, [rcx+2Ch]
0x14000a126  test    al, 40h
0x14000a128  jz      loc_140009EBC
0x14000a12e  mov     edx, 3Bh ; ';'
0x14000a133  mov     rcx, [rcx+18h]
0x14000a137  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000a13e  mov     r9d, ebx
0x14000a141  call    WPP_SF_d
0x14000a146  jmp     loc_140009EBC
0x14000a14b  mov     rcx, rdi
0x14000a14e  call    XdrDecodeInt_0
0x14000a153  mov     rcx, [rdi+408h]
0x14000a15a  cmp     eax, [rcx+13Ch]
0x14000a160  jz      loc_140009EBC
0x14000a166  mov     ebx, 0C0000022h
0x14000a16b  jmp     loc_140009EBC
0x14000a170  xor     eax, eax
0x14000a172  add     rsp, 48h
0x14000a176  pop     r15
0x14000a178  pop     r14
0x14000a17a  pop     r13
0x14000a17c  pop     r12
0x14000a17e  pop     rdi
0x14000a17f  pop     rsi
0x14000a180  pop     rbp
0x14000a181  pop     rbx
0x14000a182  retn
```
