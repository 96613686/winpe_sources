# HUBDESC_InternalValidateStringDescriptor

- ea: `0x1400399c4`
- end: `0x140039cc7`
- name: `HUBDESC_InternalValidateStringDescriptor`
- size: `771`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x140024970`
- `0x140024af0`
- `0x14002cbe0`
- `0x14002cda0`
- `0x14002cf60`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x1400067ac`
- `0x1400399c4`
- `0x14003f208`
- `0x140045570`

## pseudocode

```c
char __fastcall HUBDESC_InternalValidateStringDescriptor(
        char *a1,
        unsigned int a2,
        unsigned int *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  unsigned int v7; // ebx
  int v8; // ebp
  char v9; // bl
  unsigned int v11; // eax
  void (__fastcall **v12)(_QWORD, __int64); // r14
  _QWORD *v13; // r15
  char v14; // al
  void (__fastcall **v15)(_QWORD, __int64); // rax
  char v16; // al
  int v17; // eax
  char v18; // [rsp+28h] [rbp-60h]
  void (__fastcall **v19)(_QWORD, __int64); // [rsp+40h] [rbp-48h]
  int v21; // [rsp+98h] [rbp+10h]
  _QWORD *v22; // [rsp+A8h] [rbp+20h]

  v7 = a2;
  if ( a2 >= 2 )
  {
    v11 = (unsigned __int8)*a1;
    v8 = a5;
    v21 = 0;
    *a3 = v11;
    if ( v11 <= a2 )
    {
      v12 = (void (__fastcall **)(_QWORD, __int64))(a6 + 24);
      v13 = (_QWORD *)(a6 + 40);
    }
    else
    {
      v21 = 2;
      *a3 = a2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_Ddd(a5, a2, (_DWORD)a3, 253);
      v12 = (void (__fastcall **)(_QWORD, __int64))(a6 + 24);
      v13 = (_QWORD *)(a6 + 40);
      (*(void (__fastcall **)(_QWORD, __int64))(a6 + 24))(*(_QWORD *)(a6 + 40), 129);
    }
    if ( (unsigned __int8)*a1 > 2u )
    {
      v22 = v13;
      v19 = v12;
    }
    else
    {
      v21 = 2;
      *a3 = v7;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v22 = v13;
        v19 = v12;
      }
      else
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_d(a5, a2, 5, 254, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v7);
        v22 = (_QWORD *)(a6 + 40);
        v19 = (void (__fastcall **)(_QWORD, __int64))(a6 + 24);
      }
      (*v12)(*v13, 130);
    }
    v14 = a1[1];
    if ( v14 != 3 )
    {
      v21 = 2;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v22 = v13;
        v15 = v12;
      }
      else
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_dD(a5, a2, 5, 255, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v14, 3);
        v15 = v19;
      }
      (*v15)(*v22, 133);
    }
    v16 = *a1;
    if ( (*a1 & 1) != 0 )
    {
      *a3 &= ~1u;
      v21 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_dD(a5, a2, 5, 256, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v16, *a3);
      }
      (*v12)(*v13, 128);
    }
    v17 = (unsigned __int8)*a1;
    if ( v17 != v7 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_dD(a5, a2, 5, 257, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v17, v7);
      }
      (*v12)(*v13, 134);
    }
    if ( !v21 )
      return 1;
  }
  else
  {
    *a3 = 0;
    v8 = a5;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v18 = a2;
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(a5, a2, 5, 252, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v18);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(a6 + 24))(*(_QWORD *)(a6 + 40), 131);
  }
  v9 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_(v8, a2, 5, 258, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  }
  return v9;
}

```

## disassembly

```asm
0x1400399c4  mov     rax, rsp
0x1400399c7  mov     [rax+20h], r9
0x1400399cb  mov     [rax+8], rcx
0x1400399cf  push    rbx
0x1400399d0  push    rbp
0x1400399d1  push    rsi
0x1400399d2  push    rdi
0x1400399d3  push    r13
0x1400399d5  push    r14
0x1400399d7  push    r15
0x1400399d9  sub     rsp, 50h
0x1400399dd  mov     rsi, r8
0x1400399e0  mov     ebx, edx
0x1400399e2  cmp     edx, 2
0x1400399e5  jnb     loc_140039A80
0x1400399eb  mov     dword ptr [r8], 0
0x1400399f2  mov     rbp, [rsp+88h+arg_20]; __annotation("TMF:",
0x1400399fa  lea     rdi, WPP_RECORDER_INITIALIZED
0x140039a01  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140039a08  lea     rsi, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140039a0f  jz      short loc_140039A2E
0x140039a11  mov     [rax-60h], edx
0x140039a14  mov     r9d, 0FCh
0x140039a1a  mov     dl, 2
0x140039a1c  mov     [rax-68h], rsi
0x140039a20  mov     r8d, 5
0x140039a26  mov     rcx, rbp
0x140039a29  call    WPP_RECORDER_SF_d
0x140039a2e  mov     rcx, [rsp+88h+arg_28]
0x140039a36  mov     edx, 83h
0x140039a3b  mov     rax, [rcx+18h]
0x140039a3f  mov     rcx, [rcx+28h]
0x140039a43  call    _guard_dispatch_icall
0x140039a48  xor     bl, bl
0x140039a4a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140039a51  jz      short loc_140039A6E
0x140039a53  mov     r9d, 102h
0x140039a59  mov     [rsp+88h+var_68], rsi
0x140039a5e  mov     r8d, 5
0x140039a64  mov     dl, 2
0x140039a66  mov     rcx, rbp
0x140039a69  call    WPP_RECORDER_SF_
0x140039a6e  mov     al, bl
0x140039a70  add     rsp, 50h
0x140039a74  pop     r15
0x140039a76  pop     r14
0x140039a78  pop     r13
0x140039a7a  pop     rdi
0x140039a7b  pop     rsi
0x140039a7c  pop     rbp
0x140039a7d  pop     rbx
0x140039a7e  retn
0x140039a80  movzx   eax, byte ptr [rcx]
0x140039a83  lea     rdi, WPP_RECORDER_INITIALIZED
0x140039a8a  mov     r13, [rsp+88h+arg_28]
0x140039a92  mov     rbp, [rsp+88h+arg_20]
0x140039a9a  mov     [rsp+88h+arg_8], 0
0x140039aa5  mov     [r8], eax
0x140039aa8  cmp     eax, ebx
0x140039aaa  jbe     short loc_140039AF7
0x140039aac  mov     [rsp+88h+arg_8], 2
0x140039ab7  mov     [r8], ebx
0x140039aba  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140039ac1  jz      short loc_140039ADD
0x140039ac3  mov     [rsp+88h+var_50], ebx
0x140039ac7  mov     r9d, 0FDh
0x140039acd  mov     [rsp+88h+var_58], eax
0x140039ad1  mov     rcx, rbp
0x140039ad4  mov     dword ptr [rsp+88h+var_60], ebx
0x140039ad8  call    WPP_RECORDER_SF_Ddd
0x140039add  lea     r14, [r13+18h]
0x140039ae1  mov     edx, 81h
0x140039ae6  mov     rax, [r14]
0x140039ae9  lea     r15, [r13+28h]
0x140039aed  mov     rcx, [r15]
0x140039af0  call    _guard_dispatch_icall
0x140039af5  jmp     short loc_140039AFF
0x140039af7  lea     r14, [r13+18h]
0x140039afb  lea     r15, [r13+28h]
0x140039aff  mov     rax, [rsp+88h+arg_0]
0x140039b07  lea     rcx, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140039b0e  cmp     byte ptr [rax], 2
0x140039b11  ja      short loc_140039B85
0x140039b13  mov     [rsp+88h+arg_8], 2
0x140039b1e  mov     [rsi], ebx
0x140039b20  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140039b27  jz      short loc_140039B5F
0x140039b29  mov     dword ptr [rsp+88h+var_60], ebx
0x140039b2d  mov     r9d, 0FEh
0x140039b33  mov     [rsp+88h+var_68], rcx
0x140039b38  mov     r8d, 5
0x140039b3e  mov     rcx, rbp
0x140039b41  mov     dl, 2
0x140039b43  call    WPP_RECORDER_SF_d
0x140039b48  lea     rax, [r13+18h]
0x140039b4c  add     r13, 28h ; '('
0x140039b50  mov     [rsp+88h+arg_18], r13
0x140039b58  mov     [rsp+88h+var_48], rax
0x140039b5d  jmp     short loc_140039B6C
0x140039b5f  mov     [rsp+88h+arg_18], r15
0x140039b67  mov     [rsp+88h+var_48], r14
0x140039b6c  mov     rax, [r14]
0x140039b6f  mov     edx, 82h
0x140039b74  mov     rcx, [r15]
0x140039b77  call    _guard_dispatch_icall
0x140039b7c  lea     rcx, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140039b83  jmp     short loc_140039B92
0x140039b85  mov     [rsp+88h+arg_18], r15
0x140039b8d  mov     [rsp+88h+var_48], r14
0x140039b92  mov     r13, [rsp+88h+arg_0]
0x140039b9a  movzx   eax, byte ptr [r13+1]
0x140039b9f  cmp     al, 3
0x140039ba1  jz      short loc_140039C08
0x140039ba3  mov     [rsp+88h+arg_8], 2
0x140039bae  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140039bb5  jz      short loc_140039BE5
0x140039bb7  mov     [rsp+88h+var_58], 3
0x140039bbf  mov     r9d, 0FFh
0x140039bc5  mov     dword ptr [rsp+88h+var_60], eax
0x140039bc9  mov     r8d, 5
0x140039bcf  mov     [rsp+88h+var_68], rcx
0x140039bd4  mov     dl, 2
0x140039bd6  mov     rcx, rbp
0x140039bd9  call    WPP_RECORDER_SF_dD
0x140039bde  mov     rax, [rsp+88h+var_48]
0x140039be3  jmp     short loc_140039BF0
0x140039be5  mov     [rsp+88h+arg_18], r15
0x140039bed  mov     rax, r14
0x140039bf0  mov     rcx, [rsp+88h+arg_18]
0x140039bf8  mov     edx, 85h
0x140039bfd  mov     rax, [rax]
0x140039c00  mov     rcx, [rcx]
0x140039c03  call    _guard_dispatch_icall
0x140039c08  movzx   eax, byte ptr [r13+0]
0x140039c0d  test    al, 1
0x140039c0f  jz      short loc_140039C66
0x140039c11  and     dword ptr [rsi], 0FFFFFFFEh
0x140039c14  mov     ecx, [rsi]
0x140039c16  mov     [rsp+88h+arg_8], 2
0x140039c21  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140039c28  lea     rsi, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140039c2f  jz      short loc_140039C54
0x140039c31  mov     [rsp+88h+var_58], ecx
0x140039c35  mov     r9d, 100h
0x140039c3b  mov     dword ptr [rsp+88h+var_60], eax
0x140039c3f  mov     rcx, rbp
0x140039c42  mov     r8d, 5
0x140039c48  mov     [rsp+88h+var_68], rsi
0x140039c4d  mov     dl, 2
0x140039c4f  call    WPP_RECORDER_SF_dD
0x140039c54  mov     rax, [r14]
0x140039c57  mov     edx, 80h
0x140039c5c  mov     rcx, [r15]
0x140039c5f  call    _guard_dispatch_icall
0x140039c64  jmp     short loc_140039C6D
0x140039c66  lea     rsi, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140039c6d  movzx   eax, byte ptr [r13+0]
0x140039c72  cmp     eax, ebx
0x140039c74  jz      short loc_140039CB2
0x140039c76  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140039c7d  jz      short loc_140039CA2
0x140039c7f  mov     [rsp+88h+var_58], ebx
0x140039c83  mov     r9d, 101h
0x140039c89  mov     dword ptr [rsp+88h+var_60], eax
0x140039c8d  mov     r8d, 5
0x140039c93  mov     dl, 2
0x140039c95  mov     [rsp+88h+var_68], rsi
0x140039c9a  mov     rcx, rbp
0x140039c9d  call    WPP_RECORDER_SF_dD
0x140039ca2  mov     rax, [r14]
0x140039ca5  mov     edx, 86h
0x140039caa  mov     rcx, [r15]
0x140039cad  call    _guard_dispatch_icall
0x140039cb2  cmp     [rsp+88h+arg_8], 0
0x140039cba  jnz     loc_140039A48
0x140039cc0  mov     bl, 1
0x140039cc2  jmp     loc_140039A6E
```
