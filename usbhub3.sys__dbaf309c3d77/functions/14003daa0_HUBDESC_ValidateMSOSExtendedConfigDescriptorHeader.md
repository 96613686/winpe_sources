# HUBDESC_ValidateMSOSExtendedConfigDescriptorHeader

- ea: `0x14003daa0`
- end: `0x14003dce6`
- name: `HUBDESC_ValidateMSOSExtendedConfigDescriptorHeader`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140025300`

## callees

- `0x1400025a4`
- `0x1400067ac`
- `0x14003daa0`
- `0x140045570`

## pseudocode

```c
char __fastcall HUBDESC_ValidateMSOSExtendedConfigDescriptorHeader(__int64 a1, int a2, __int64 a3, int a4)
{
  int v4; // r13d
  __int64 v6; // rax
  int v7; // edx
  char v8; // bl
  __int16 v9; // cx
  int v10; // edx
  void (__fastcall **v11)(_QWORD, __int64); // r14
  _QWORD *v12; // r15
  __int16 v13; // cx
  void (__fastcall **v14)(_QWORD, __int64); // r13
  _QWORD *v15; // rsi
  char v17; // [rsp+28h] [rbp-40h]

  v4 = a4;
  v6 = a1;
  if ( a2 == 16 )
  {
    v9 = *(_WORD *)(a1 + 4);
    v10 = 256;
    v8 = 1;
    if ( v9 == 256 )
    {
      v11 = (void (__fastcall **)(_QWORD, __int64))(a3 + 24);
      v12 = (_QWORD *)(a3 + 40);
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_dD(a4, v10, 5, 287, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v9, 0);
      }
      v11 = (void (__fastcall **)(_QWORD, __int64))(a3 + 24);
      v12 = (_QWORD *)(a3 + 40);
      (*(void (__fastcall **)(_QWORD, __int64))(a3 + 24))(*(_QWORD *)(a3 + 40), 120);
      v6 = a1;
      v8 = 0;
    }
    v13 = *(_WORD *)(v6 + 6);
    v7 = 4;
    if ( v13 == 4 )
    {
      v15 = v12;
      v14 = v11;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v15 = v12;
        v14 = v11;
      }
      else
      {
        LOBYTE(v7) = 2;
        WPP_RECORDER_SF_dD(v4, v7, 5, 288, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v13, 4);
        v14 = (void (__fastcall **)(_QWORD, __int64))(a3 + 24);
        v15 = (_QWORD *)(a3 + 40);
      }
      (*v11)(*v12, 125);
      v6 = a1;
      v8 = 0;
    }
    if ( *(_BYTE *)(v6 + 8) == 1 )
    {
      if ( *(_DWORD *)v6 == 40 )
      {
        if ( v8 )
          return v8;
      }
      else
      {
        v8 = 0;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v7) = 2;
          WPP_RECORDER_SF_dD(
            a4,
            v7,
            5,
            290,
            (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
            *(_DWORD *)v6,
            40);
        }
        (*v14)(*v15, 127);
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v15 = v12;
        v14 = v11;
      }
      else
      {
        LOBYTE(v7) = 2;
        WPP_RECORDER_SF_(a4, v7, 5, 289, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
      }
      (*v14)(*v15, 121);
      v8 = 0;
    }
    v4 = a4;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v17 = a2;
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_dD(a4, a2, 5, 286, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v17, 16);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(a3 + 24))(*(_QWORD *)(a3 + 40), 122);
    v8 = 0;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_(v4, v7, 5, 291, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  }
  return v8;
}

```

## disassembly

```asm
0x14003daa0  mov     r11, rsp
0x14003daa3  mov     [r11+10h], rbx
0x14003daa7  mov     [r11+18h], rsi
0x14003daab  mov     [r11+20h], r9
0x14003daaf  mov     [r11+8], rcx
0x14003dab3  push    rdi
0x14003dab4  push    r12
0x14003dab6  push    r13
0x14003dab8  push    r14
0x14003daba  push    r15
0x14003dabc  sub     rsp, 40h
0x14003dac0  mov     r13, r9
0x14003dac3  mov     rsi, r8
0x14003dac6  mov     rax, rcx
0x14003dac9  cmp     edx, 10h
0x14003dacc  jz      short loc_14003DB24
0x14003dace  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003dad5  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003dadc  lea     r12, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003dae3  jz      short loc_14003DB0B
0x14003dae5  mov     [rsp+68h+var_38], 10h
0x14003daed  mov     r9d, 11Eh
0x14003daf3  mov     dword ptr [rsp+68h+var_40], edx
0x14003daf7  mov     r8d, 5
0x14003dafd  mov     dl, 2
0x14003daff  mov     [r11-48h], r12
0x14003db03  mov     rcx, r13
0x14003db06  call    WPP_RECORDER_SF_dD
0x14003db0b  mov     rax, [rsi+18h]
0x14003db0f  mov     edx, 7Ah ; 'z'
0x14003db14  mov     rcx, [rsi+28h]
0x14003db18  call    _guard_dispatch_icall
0x14003db1d  xor     bl, bl
0x14003db1f  jmp     loc_14003DCA5
0x14003db24  movzx   ecx, word ptr [rcx+4]
0x14003db28  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003db2f  mov     edx, 100h
0x14003db34  lea     r12, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003db3b  mov     bl, 1
0x14003db3d  cmp     cx, dx
0x14003db40  jz      short loc_14003DB8D
0x14003db42  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14003db49  jz      short loc_14003DB6C
0x14003db4b  mov     [rsp+68h+var_38], edx
0x14003db4f  lea     r9d, [rdx+1Fh]
0x14003db53  mov     dword ptr [rsp+68h+var_40], ecx
0x14003db57  mov     r8d, 5
0x14003db5d  mov     rcx, r13
0x14003db60  mov     [rsp+68h+var_48], r12
0x14003db65  mov     dl, 2
0x14003db67  call    WPP_RECORDER_SF_dD
0x14003db6c  lea     r14, [rsi+18h]
0x14003db70  mov     edx, 78h ; 'x'
0x14003db75  mov     rax, [r14]
0x14003db78  lea     r15, [rsi+28h]
0x14003db7c  mov     rcx, [r15]
0x14003db7f  call    _guard_dispatch_icall
0x14003db84  mov     rax, [rsp+68h+arg_0]
0x14003db89  xor     bl, bl
0x14003db8b  jmp     short loc_14003DB95
0x14003db8d  lea     r14, [r8+18h]
0x14003db91  lea     r15, [r8+28h]
0x14003db95  movzx   ecx, word ptr [rax+6]
0x14003db99  mov     edx, 4
0x14003db9e  cmp     cx, dx
0x14003dba1  jz      short loc_14003DBF6
0x14003dba3  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14003dbaa  jz      short loc_14003DBD7
0x14003dbac  mov     [rsp+68h+var_38], edx
0x14003dbb0  lea     r8d, [rdx+1]
0x14003dbb4  mov     dword ptr [rsp+68h+var_40], ecx
0x14003dbb8  mov     r9d, 120h
0x14003dbbe  mov     rcx, r13
0x14003dbc1  mov     [rsp+68h+var_48], r12
0x14003dbc6  mov     dl, 2
0x14003dbc8  call    WPP_RECORDER_SF_dD
0x14003dbcd  lea     r13, [rsi+18h]
0x14003dbd1  add     rsi, 28h ; '('
0x14003dbd5  jmp     short loc_14003DBDD
0x14003dbd7  mov     rsi, r15
0x14003dbda  mov     r13, r14
0x14003dbdd  mov     rax, [r14]
0x14003dbe0  mov     edx, 7Dh ; '}'
0x14003dbe5  mov     rcx, [r15]
0x14003dbe8  call    _guard_dispatch_icall
0x14003dbed  mov     rax, [rsp+68h+arg_0]
0x14003dbf2  xor     bl, bl
0x14003dbf4  jmp     short loc_14003DBFC
0x14003dbf6  mov     rsi, r15
0x14003dbf9  mov     r13, r14
0x14003dbfc  cmp     byte ptr [rax+8], 1
0x14003dc00  jz      short loc_14003DC48
0x14003dc02  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14003dc09  jz      short loc_14003DC2D
0x14003dc0b  mov     rcx, [rsp+68h+arg_18]
0x14003dc13  mov     r9d, 121h
0x14003dc19  mov     r8d, 5
0x14003dc1f  mov     [rsp+68h+var_48], r12
0x14003dc24  mov     dl, 2
0x14003dc26  call    WPP_RECORDER_SF_
0x14003dc2b  jmp     short loc_14003DC33
0x14003dc2d  mov     rsi, r15
0x14003dc30  mov     r13, r14
0x14003dc33  mov     rax, [r13+0]
0x14003dc37  mov     edx, 79h ; 'y'
0x14003dc3c  mov     rcx, [rsi]
0x14003dc3f  call    _guard_dispatch_icall
0x14003dc44  xor     bl, bl
0x14003dc46  jmp     short loc_14003DC9D
0x14003dc48  mov     ecx, [rax]
0x14003dc4a  cmp     ecx, 28h ; '('
0x14003dc4d  jz      short loc_14003DC99
0x14003dc4f  xor     bl, bl
0x14003dc51  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14003dc58  jz      short loc_14003DC86
0x14003dc5a  mov     [rsp+68h+var_38], 28h ; '('
0x14003dc62  mov     r9d, 122h
0x14003dc68  mov     dword ptr [rsp+68h+var_40], ecx
0x14003dc6c  mov     r8d, 5
0x14003dc72  mov     rcx, [rsp+68h+arg_18]
0x14003dc7a  mov     dl, 2
0x14003dc7c  mov     [rsp+68h+var_48], r12
0x14003dc81  call    WPP_RECORDER_SF_dD
0x14003dc86  mov     rax, [r13+0]
0x14003dc8a  mov     edx, 7Fh
0x14003dc8f  mov     rcx, [rsi]
0x14003dc92  call    _guard_dispatch_icall
0x14003dc97  jmp     short loc_14003DC9D
0x14003dc99  test    bl, bl
0x14003dc9b  jnz     short loc_14003DCC9
0x14003dc9d  mov     r13, [rsp+68h+arg_18]
0x14003dca5  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14003dcac  jz      short loc_14003DCC9
0x14003dcae  mov     r9d, 123h
0x14003dcb4  mov     [rsp+68h+var_48], r12
0x14003dcb9  mov     r8d, 5
0x14003dcbf  mov     dl, 2
0x14003dcc1  mov     rcx, r13
0x14003dcc4  call    WPP_RECORDER_SF_
0x14003dcc9  lea     r11, [rsp+68h+var_28]
0x14003dcce  mov     al, bl
0x14003dcd0  mov     rbx, [r11+38h]
0x14003dcd4  mov     rsi, [r11+40h]
0x14003dcd8  mov     rsp, r11
0x14003dcdb  pop     r15
0x14003dcdd  pop     r14
0x14003dcdf  pop     r13
0x14003dce1  pop     r12
0x14003dce3  pop     rdi
0x14003dce4  retn
```
