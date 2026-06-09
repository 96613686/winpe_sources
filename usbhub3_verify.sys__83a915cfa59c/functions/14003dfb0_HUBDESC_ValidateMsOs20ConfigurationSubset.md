# HUBDESC_ValidateMsOs20ConfigurationSubset

- ea: `0x14003dfb0`
- end: `0x14003e292`
- name: `HUBDESC_ValidateMsOs20ConfigurationSubset`
- size: `738`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x140035764`
- `0x14003dfb0`
- `0x14003e5f0`
- `0x140045530`
- `0x140045570`
- `0x140045940`

## pseudocode

```c
char __fastcall HUBDESC_ValidateMsOs20ConfigurationSubset(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int64 a4)
{
  int v8; // edx
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned __int64 v11; // r15
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  unsigned __int8 (__fastcall *v14)(__int64, _BYTE *, unsigned __int16 *, unsigned __int64); // r12
  int v15; // edx
  char result; // al
  int v17; // r9d
  __int64 v18; // [rsp+28h] [rbp-D0h]
  unsigned __int16 *v19; // [rsp+30h] [rbp-C8h] BYREF
  _BYTE v20[112]; // [rsp+40h] [rbp-B8h] BYREF

  memset(v20, 0, 0x68u);
  if ( *a3 != 8 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_d(*(_QWORD *)(a2 + 96), v8, 5, 322, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, *a3);
    }
    v9 = 156;
    goto LABEL_35;
  }
  v10 = a3[3];
  if ( (unsigned int)v10 < 0xC )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_d(*(_QWORD *)(a2 + 96), v8, 5, 323, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v10);
    }
    v9 = 157;
    goto LABEL_35;
  }
  v11 = (unsigned __int64)a3 + v10;
  if ( (unsigned __int64)a3 + v10 <= a4 )
  {
    v12 = a3 + 4;
    v19 = v12;
    if ( (unsigned __int64)v12 > v11
      || (unsigned __int64)(v12 + 2) > v11
      || (v13 = *v12, (unsigned int)v13 < 4)
      || (unsigned __int64)v12 + v13 > v11 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_34:
        v9 = 160;
        goto LABEL_35;
      }
      v17 = 325;
    }
    else
    {
      while ( 1 )
      {
        if ( v12[1] >= 9u )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LODWORD(v18) = v12[1];
            LOBYTE(v8) = 2;
            WPP_RECORDER_SF_d(
              *(_QWORD *)(a2 + 96),
              v8,
              5,
              327,
              (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
              v18);
          }
        }
        else
        {
          v14 = (unsigned __int8 (__fastcall *)(__int64, _BYTE *, unsigned __int16 *, unsigned __int64))*(&MsOs20DispatchTable + 2 * v12[1]);
          if ( !*((_BYTE *)&MsOs20DispatchTable + 16 * v12[1] + 8) )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LODWORD(v18) = v12[1];
              LOBYTE(v8) = 2;
              WPP_RECORDER_SF_d(
                *(_QWORD *)(a2 + 96),
                v8,
                5,
                326,
                (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                v18);
            }
            (*(void (__fastcall **)(_QWORD, __int64))(a1 + 32))(*(_QWORD *)(a1 + 40), 159);
          }
          if ( !v14(a1, v20, v12, v11) )
            goto LABEL_36;
        }
        if ( !(unsigned __int8)HUBDESC_GetNextMsOs20Descriptor(v11, &v19) )
          break;
        v12 = v19;
        if ( !v19 )
        {
          *(_DWORD *)a2 |= 8u;
          return 1;
        }
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_34;
      v17 = 328;
    }
    LOBYTE(v8) = 2;
    WPP_RECORDER_SF_(*(_QWORD *)(a2 + 96), v8, 5, v17, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
    goto LABEL_34;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v8) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(a2 + 96), v8, 5, 324, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v10);
  }
  v9 = 158;
LABEL_35:
  (*(void (__fastcall **)(_QWORD, __int64))(a1 + 24))(*(_QWORD *)(a1 + 40), v9);
LABEL_36:
  result = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v15) = 2;
    WPP_RECORDER_SF_(*(_QWORD *)(a2 + 96), v15, 5, 329, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14003dfb0  mov     [rsp+arg_18], rbx
0x14003dfb5  push    rbp
0x14003dfb6  push    rsi
0x14003dfb7  push    rdi
0x14003dfb8  push    r12
0x14003dfba  push    r13
0x14003dfbc  push    r14
0x14003dfbe  push    r15
0x14003dfc0  sub     rsp, 0C0h
0x14003dfc7  mov     rax, cs:__security_cookie
0x14003dfce  xor     rax, rsp
0x14003dfd1  mov     [rsp+0F8h+var_48], rax
0x14003dfd9  mov     r14, rdx
0x14003dfdc  mov     rsi, r8
0x14003dfdf  xor     edx, edx; Val
0x14003dfe1  mov     rbp, rcx
0x14003dfe4  lea     rcx, [rsp+0F8h+var_B8]; void *
0x14003dfe9  mov     rbx, r9
0x14003dfec  lea     r8d, [rdx+68h]; Size
0x14003dff0  call    memset
0x14003dff5  movzx   eax, word ptr [rsi]
0x14003dff8  mov     ecx, 8
0x14003dffd  cmp     ax, cx
0x14003e000  jz      short loc_14003E041
0x14003e002  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003e009  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003e010  lea     rdi, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003e017  jz      short loc_14003E037
0x14003e019  lea     r8d, [rcx-3]
0x14003e01d  mov     dword ptr [rsp+0F8h+var_D0], eax
0x14003e021  mov     rcx, [r14+60h]
0x14003e025  mov     r9d, 142h
0x14003e02b  mov     dl, 2
0x14003e02d  mov     [rsp+0F8h+var_D8], rdi
0x14003e032  call    WPP_RECORDER_SF_d
0x14003e037  mov     edx, 9Ch
0x14003e03c  jmp     loc_14003E230
0x14003e041  movzx   ecx, word ptr [rsi+6]
0x14003e045  cmp     ecx, 0Ch
0x14003e048  jnb     short loc_14003E08B
0x14003e04a  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003e051  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003e058  lea     rdi, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003e05f  jz      short loc_14003E081
0x14003e061  mov     dword ptr [rsp+0F8h+var_D0], ecx
0x14003e065  mov     r9d, 143h
0x14003e06b  mov     rcx, [r14+60h]
0x14003e06f  mov     r8d, 5
0x14003e075  mov     dl, 2
0x14003e077  mov     [rsp+0F8h+var_D8], rdi
0x14003e07c  call    WPP_RECORDER_SF_d
0x14003e081  mov     edx, 9Dh
0x14003e086  jmp     loc_14003E230
0x14003e08b  lea     r15, [rsi+rcx]
0x14003e08f  cmp     r15, rbx
0x14003e092  jbe     short loc_14003E0D5
0x14003e094  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003e09b  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003e0a2  lea     rdi, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003e0a9  jz      short loc_14003E0CB
0x14003e0ab  mov     dword ptr [rsp+0F8h+var_D0], ecx
0x14003e0af  mov     r9d, 144h
0x14003e0b5  mov     rcx, [r14+60h]
0x14003e0b9  mov     r8d, 5
0x14003e0bf  mov     dl, 2
0x14003e0c1  mov     [rsp+0F8h+var_D8], rdi
0x14003e0c6  call    WPP_RECORDER_SF_d
0x14003e0cb  mov     edx, 9Eh
0x14003e0d0  jmp     loc_14003E230
0x14003e0d5  add     rsi, 8
0x14003e0d9  mov     [rsp+0F8h+var_C8], rsi
0x14003e0de  cmp     rsi, r15
0x14003e0e1  ja      loc_14003E1F8
0x14003e0e7  lea     rax, [rsi+4]
0x14003e0eb  cmp     rax, r15
0x14003e0ee  ja      loc_14003E1F8
0x14003e0f4  movzx   eax, word ptr [rsi]
0x14003e0f7  cmp     eax, 4
0x14003e0fa  jb      loc_14003E1F8
0x14003e100  add     rax, rsi
0x14003e103  cmp     rax, r15
0x14003e106  ja      loc_14003E1F8
0x14003e10c  lea     rbx, WPP_RECORDER_INITIALIZED
0x14003e113  lea     rdi, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003e11a  lea     r13, MsOs20DispatchTable
0x14003e121  movzx   ecx, word ptr [rsi+2]
0x14003e125  cmp     ecx, 9
0x14003e128  jnb     short loc_14003E197
0x14003e12a  mov     eax, ecx
0x14003e12c  add     rax, rax
0x14003e12f  cmp     byte ptr [r13+rax*8+8], 0
0x14003e135  mov     r12, (MsOs20DispatchTable - 14006B000h)[r13+rax*8]
0x14003e13a  jnz     short loc_14003E177
0x14003e13c  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14003e143  jz      short loc_14003E165
0x14003e145  mov     dword ptr [rsp+0F8h+var_D0], ecx
0x14003e149  mov     r9d, 146h
0x14003e14f  mov     rcx, [r14+60h]
0x14003e153  mov     r8d, 5
0x14003e159  mov     dl, 2
0x14003e15b  mov     [rsp+0F8h+var_D8], rdi
0x14003e160  call    WPP_RECORDER_SF_d
0x14003e165  mov     rax, [rbp+20h]
0x14003e169  mov     edx, 9Fh
0x14003e16e  mov     rcx, [rbp+28h]
0x14003e172  call    _guard_dispatch_icall
0x14003e177  mov     r9, r15
0x14003e17a  lea     rdx, [rsp+0F8h+var_B8]
0x14003e17f  mov     r8, rsi
0x14003e182  mov     rcx, rbp
0x14003e185  mov     rax, r12
0x14003e188  call    _guard_dispatch_icall
0x14003e18d  test    al, al
0x14003e18f  jz      loc_14003E23D
0x14003e195  jmp     short loc_14003E1C0
0x14003e197  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14003e19e  jz      short loc_14003E1C0
0x14003e1a0  mov     dword ptr [rsp+0F8h+var_D0], ecx
0x14003e1a4  mov     r9d, 147h
0x14003e1aa  mov     rcx, [r14+60h]
0x14003e1ae  mov     r8d, 5
0x14003e1b4  mov     dl, 2
0x14003e1b6  mov     [rsp+0F8h+var_D8], rdi
0x14003e1bb  call    WPP_RECORDER_SF_d
0x14003e1c0  lea     rdx, [rsp+0F8h+var_C8]
0x14003e1c5  mov     rcx, r15
0x14003e1c8  call    HUBDESC_GetNextMsOs20Descriptor
0x14003e1cd  test    al, al
0x14003e1cf  jz      short loc_14003E1E7
0x14003e1d1  mov     rsi, [rsp+0F8h+var_C8]
0x14003e1d6  test    rsi, rsi
0x14003e1d9  jnz     loc_14003E121
0x14003e1df  or      dword ptr [r14], 8
0x14003e1e3  mov     al, 1
0x14003e1e5  jmp     short loc_14003E266
0x14003e1e7  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14003e1ee  jz      short loc_14003E22B
0x14003e1f0  mov     r9d, 148h
0x14003e1f6  jmp     short loc_14003E215
0x14003e1f8  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003e1ff  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003e206  lea     rdi, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003e20d  jz      short loc_14003E22B
0x14003e20f  mov     r9d, 145h
0x14003e215  mov     rcx, [r14+60h]
0x14003e219  mov     r8d, 5
0x14003e21f  mov     dl, 2
0x14003e221  mov     [rsp+0F8h+var_D8], rdi
0x14003e226  call    WPP_RECORDER_SF_
0x14003e22b  mov     edx, 0A0h
0x14003e230  mov     rcx, [rbp+28h]
0x14003e234  mov     rax, [rbp+18h]
0x14003e238  call    _guard_dispatch_icall
0x14003e23d  xor     al, al; __annotation("TMF:",
0x14003e23f  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003e246  jz      short loc_14003E266
0x14003e248  mov     rcx, [r14+60h]
0x14003e24c  mov     r9d, 149h
0x14003e252  mov     r8d, 5
0x14003e258  mov     [rsp+0F8h+var_D8], rdi
0x14003e25d  mov     dl, 2
0x14003e25f  call    WPP_RECORDER_SF_
0x14003e264  xor     al, al
0x14003e266  mov     rcx, [rsp+0F8h+var_48]
0x14003e26e  xor     rcx, rsp; StackCookie
0x14003e271  call    __security_check_cookie
0x14003e276  mov     rbx, [rsp+0F8h+arg_18]
0x14003e27e  add     rsp, 0C0h
0x14003e285  pop     r15
0x14003e287  pop     r14
0x14003e289  pop     r13
0x14003e28b  pop     r12
0x14003e28d  pop     rdi
0x14003e28e  pop     rsi
0x14003e28f  pop     rbp
0x14003e290  retn
```
