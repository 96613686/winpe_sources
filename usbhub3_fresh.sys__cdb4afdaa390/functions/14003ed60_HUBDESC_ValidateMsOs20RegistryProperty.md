# HUBDESC_ValidateMsOs20RegistryProperty

- ea: `0x14003ed60`
- end: `0x14003ef94`
- name: `HUBDESC_ValidateMsOs20RegistryProperty`
- size: `564`
- prototype: `char __fastcall(__int64, __int64, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x14003ed60`
- `0x140045570`

## pseudocode

```c
char __fastcall HUBDESC_ValidateMsOs20RegistryProperty(__int64 a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // rbp
  __int64 v5; // rcx
  __int64 v6; // rdx
  int v7; // edx
  char v8; // bl
  __int64 v9; // rcx
  unsigned __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rcx

  v3 = a2;
  if ( *a3 < 0xDu )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v5 = *(_QWORD *)(a2 + 96);
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(v5, a2, 5, 345, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, *a3);
    }
    v6 = 169;
LABEL_5:
    (*(void (__fastcall **)(_QWORD, __int64))(a1 + 24))(*(_QWORD *)(a1 + 40), v6);
    v8 = 0;
    goto LABEL_29;
  }
  v9 = a3[3];
  v10 = *a3;
  if ( v10 < v9 + 11 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v11 = *(_QWORD *)(a2 + 96);
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(v11, a2, 5, 346, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, a3[3]);
    }
    v6 = 170;
    goto LABEL_5;
  }
  v8 = 0;
  if ( !(_WORD)v9 || (v9 & 1) != 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = *(_QWORD *)(a2 + 96);
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(v14, a2, 5, 347, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, a3[3]);
    }
    v13 = 171;
  }
  else
  {
    v12 = *(unsigned __int16 *)((char *)a3 + v9 + 8);
    if ( v10 >= v12 + v9 + 10 )
    {
      if ( (_WORD)v12 )
      {
        if ( (unsigned __int16)(a3[2] - 1) <= 6u )
        {
          *(_DWORD *)v3 |= 0x40u;
          return 1;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = 2;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(v3 + 96),
            v12,
            5,
            350,
            (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
            a3[2]);
        }
        v13 = 174;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = 2;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(v3 + 96),
            v12,
            5,
            349,
            (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
            0);
        }
        v13 = 173;
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(v3 + 96),
          v12,
          5,
          348,
          (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
          *(unsigned __int16 *)((char *)a3 + v9 + 8));
      }
      v13 = 172;
    }
  }
  (*(void (__fastcall **)(_QWORD, __int64))(a1 + 24))(*(_QWORD *)(a1 + 40), v13);
LABEL_29:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_(*(_QWORD *)(v3 + 96), v7, 5, 351, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  }
  return v8;
}

```

## disassembly

```asm
0x14003ed60  push    rbx
0x14003ed62  push    rbp
0x14003ed63  push    rsi
0x14003ed64  push    rdi
0x14003ed65  push    r14
0x14003ed67  sub     rsp, 30h
0x14003ed6b  movzx   eax, word ptr [r8]
0x14003ed6f  mov     rbp, rdx
0x14003ed72  mov     r14, rcx
0x14003ed75  cmp     eax, 0Dh
0x14003ed78  jnb     short loc_14003EDCA
0x14003ed7a  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003ed81  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003ed88  lea     rsi, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003ed8f  jz      short loc_14003EDB1
0x14003ed91  mov     rcx, [rbp+60h]
0x14003ed95  mov     r9d, 159h
0x14003ed9b  mov     [rsp+58h+var_30], eax
0x14003ed9f  mov     r8d, 5
0x14003eda5  mov     dl, 2
0x14003eda7  mov     [rsp+58h+var_38], rsi
0x14003edac  call    WPP_RECORDER_SF_d
0x14003edb1  mov     edx, 0A9h
0x14003edb6  mov     rax, [r14+18h]
0x14003edba  mov     rcx, [r14+28h]
0x14003edbe  call    _guard_dispatch_icall
0x14003edc3  xor     ebx, ebx
0x14003edc5  jmp     loc_14003EF61
0x14003edca  movzx   ecx, word ptr [r8+6]
0x14003edcf  mov     r9, rax
0x14003edd2  lea     rax, [rcx+0Bh]
0x14003edd6  cmp     r9, rax
0x14003edd9  jnb     short loc_14003EE19
0x14003eddb  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003ede2  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003ede9  lea     rsi, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003edf0  jz      short loc_14003EE12
0x14003edf2  mov     [rsp+58h+var_30], ecx
0x14003edf6  mov     r9d, 15Ah
0x14003edfc  mov     rcx, [rbp+60h]
0x14003ee00  mov     r8d, 5
0x14003ee06  mov     dl, 2
0x14003ee08  mov     [rsp+58h+var_38], rsi
0x14003ee0d  call    WPP_RECORDER_SF_d
0x14003ee12  mov     edx, 0AAh
0x14003ee17  jmp     short loc_14003EDB6
0x14003ee19  xor     ebx, ebx
0x14003ee1b  test    cx, cx
0x14003ee1e  jz      loc_14003EF18
0x14003ee24  test    cl, 1
0x14003ee27  jnz     loc_14003EF18
0x14003ee2d  movzx   edx, word ptr [rcx+r8+8]
0x14003ee33  lea     rax, [rcx+0Ah]
0x14003ee37  add     rax, rdx
0x14003ee3a  cmp     r9, rax
0x14003ee3d  jnb     short loc_14003EE7E
0x14003ee3f  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003ee46  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003ee4d  lea     rsi, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003ee54  jz      short loc_14003EE74
0x14003ee56  mov     rcx, [rbp+60h]
0x14003ee5a  lea     r8d, [rbx+5]
0x14003ee5e  mov     [rsp+58h+var_30], edx
0x14003ee62  mov     r9d, 15Ch
0x14003ee68  mov     dl, 2
0x14003ee6a  mov     [rsp+58h+var_38], rsi
0x14003ee6f  call    WPP_RECORDER_SF_d
0x14003ee74  mov     edx, 0ACh
0x14003ee79  jmp     loc_14003EF54
0x14003ee7e  test    dx, dx
0x14003ee81  jnz     short loc_14003EEC4
0x14003ee83  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003ee8a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003ee91  lea     rsi, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003ee98  jz      short loc_14003EEBA
0x14003ee9a  mov     rcx, [rbp+60h]
0x14003ee9e  mov     r9d, 15Dh
0x14003eea4  mov     [rsp+58h+var_30], ebx
0x14003eea8  mov     r8d, 5
0x14003eeae  mov     dl, 2
0x14003eeb0  mov     [rsp+58h+var_38], rsi
0x14003eeb5  call    WPP_RECORDER_SF_d
0x14003eeba  mov     edx, 0ADh
0x14003eebf  jmp     loc_14003EF54
0x14003eec4  movzx   ecx, word ptr [r8+4]
0x14003eec9  lea     eax, [rcx-1]
0x14003eecc  cmp     ax, 6
0x14003eed0  jbe     short loc_14003EF10
0x14003eed2  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003eed9  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003eee0  lea     rsi, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003eee7  jz      short loc_14003EF09
0x14003eee9  mov     [rsp+58h+var_30], ecx
0x14003eeed  mov     r9d, 15Eh
0x14003eef3  mov     rcx, [rbp+60h]
0x14003eef7  mov     r8d, 5
0x14003eefd  mov     dl, 2
0x14003eeff  mov     [rsp+58h+var_38], rsi
0x14003ef04  call    WPP_RECORDER_SF_d
0x14003ef09  mov     edx, 0AEh
0x14003ef0e  jmp     short loc_14003EF54
0x14003ef10  or      dword ptr [rbp+0], 40h
0x14003ef14  mov     bl, 1
0x14003ef16  jmp     short loc_14003EF86
0x14003ef18  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003ef1f  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003ef26  lea     rsi, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003ef2d  jz      short loc_14003EF4F
0x14003ef2f  mov     [rsp+58h+var_30], ecx
0x14003ef33  mov     r9d, 15Bh
0x14003ef39  mov     rcx, [rbp+60h]
0x14003ef3d  mov     r8d, 5
0x14003ef43  mov     dl, 2
0x14003ef45  mov     [rsp+58h+var_38], rsi
0x14003ef4a  call    WPP_RECORDER_SF_d
0x14003ef4f  mov     edx, 0ABh
0x14003ef54  mov     rcx, [r14+28h]
0x14003ef58  mov     rax, [r14+18h]
0x14003ef5c  call    _guard_dispatch_icall
0x14003ef61  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14003ef68  jz      short loc_14003EF86
0x14003ef6a  mov     rcx, [rbp+60h]
0x14003ef6e  mov     r9d, 15Fh
0x14003ef74  mov     r8d, 5
0x14003ef7a  mov     [rsp+58h+var_38], rsi
0x14003ef7f  mov     dl, 2
0x14003ef81  call    WPP_RECORDER_SF_
0x14003ef86  mov     al, bl
0x14003ef88  add     rsp, 30h
0x14003ef8c  pop     r14
0x14003ef8e  pop     rdi
0x14003ef8f  pop     rsi
0x14003ef90  pop     rbp
0x14003ef91  pop     rbx
0x14003ef92  retn
```
