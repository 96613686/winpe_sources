# HUBDESC_InternalValidateCommonDescriptorHeader

- ea: `0x140035e1c`
- end: `0x1400360b6`
- name: `HUBDESC_InternalValidateCommonDescriptorHeader`
- size: `666`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14003c828`
- `0x14003cce8`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x1400067ac`
- `0x14001cf04`
- `0x14002d940`
- `0x140035e1c`
- `0x140045570`

## pseudocode

```c
char __fastcall HUBDESC_InternalValidateCommonDescriptorHeader(
        char *a1,
        __int64 a2,
        unsigned int *a3,
        int *a4,
        __int64 a5)
{
  int *v5; // rdi
  __int64 v6; // rbx
  int v8; // r15d
  unsigned int v9; // esi
  int v10; // r12d
  char v11; // si
  unsigned int v13; // eax
  unsigned int v14; // ecx
  __int64 v15; // [rsp+28h] [rbp-60h]
  int v16; // [rsp+90h] [rbp+8h] BYREF
  unsigned int v17; // [rsp+98h] [rbp+10h]
  unsigned int *v18; // [rsp+A0h] [rbp+18h]

  v18 = a3;
  v5 = a4;
  v16 = 0;
  v6 = a2;
  if ( a4 )
  {
    if ( *(_BYTE *)(a2 + 48) )
      *a4 = 0;
  }
  else
  {
    v5 = &v16;
  }
  v8 = (_DWORD)a1 - *(_DWORD *)(a2 + 56);
  v9 = *(_DWORD *)(a2 + 72) - v8;
  *a3 = 0;
  if ( v9 < 2 )
  {
    *v5 = 1;
    v10 = a5;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_dD(a5, a2, 5, 13, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v9, 2);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(v6 + 24))(*(_QWORD *)(v6 + 40), 90);
LABEL_9:
    v11 = 1;
    goto LABEL_10;
  }
  v13 = (unsigned __int8)*a1;
  v10 = a5;
  v14 = *(_DWORD *)(a2 + 64) - (_DWORD)a1;
  v17 = *(_DWORD *)(a2 + 64) - (_DWORD)a1;
  *a3 = v13;
  if ( v13 > v9 )
  {
    *v5 = 2;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_DDDD(v10, a2, 5, 14, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, *a1, v8, v9, v9);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(v6 + 24))(*(_QWORD *)(v6 + 40), 87);
    v14 = v17;
    *v18 = v9;
  }
  if ( (unsigned __int8)*a1 > v14 )
  {
    *v5 = 2;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_DDD(
        v10,
        a2,
        (_DWORD)a3,
        15,
        (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
        *a1,
        v8,
        v14);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(v6 + 24))(*(_QWORD *)(v6 + 40), 88);
  }
  if ( (unsigned __int8)*a1 < 2u )
  {
    if ( *(_WORD *)v6 > 0x200u || *(_BYTE *)(v6 + 12) )
      *v5 = 2;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_DDD(v10, a2, (_DWORD)a3, 16, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, *a1, v8, 2);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(v6 + 24))(*(_QWORD *)(v6 + 40), 89);
  }
  if ( *a1 )
    goto LABEL_9;
  if ( *(_WORD *)v6 > 0x200u || *(_BYTE *)(v6 + 12) )
  {
    v11 = 1;
    *v5 = 1;
  }
  else
  {
    v11 = 1;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v15) = v8;
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_d(v10, a2, 5, 17, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v15);
  }
  (*(void (__fastcall **)(_QWORD, __int64))(v6 + 24))(*(_QWORD *)(v6 + 40), 91);
LABEL_10:
  if ( *v5 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_(v10, a2, 5, 18, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
    }
    return 0;
  }
  return v11;
}

```

## disassembly

```asm
0x140035e1c  mov     r11, rsp
0x140035e1f  mov     [r11+20h], rbx
0x140035e23  mov     [r11+18h], r8
0x140035e27  push    rbp
0x140035e28  push    rsi
0x140035e29  push    rdi
0x140035e2a  push    r12
0x140035e2c  push    r13
0x140035e2e  push    r14
0x140035e30  push    r15
0x140035e32  sub     rsp, 50h
0x140035e36  xor     eax, eax
0x140035e38  mov     rdi, r9
0x140035e3b  mov     [r11+8], eax
0x140035e3f  mov     rbx, rdx
0x140035e42  mov     rbp, rcx
0x140035e45  test    r9, r9
0x140035e48  jnz     short loc_140035E50
0x140035e4a  lea     rdi, [r11+8]
0x140035e4e  jmp     short loc_140035E58
0x140035e50  cmp     [rdx+30h], al
0x140035e53  jz      short loc_140035E58
0x140035e55  mov     [r9], eax
0x140035e58  mov     esi, [rdx+48h]
0x140035e5b  mov     r15d, ebp
0x140035e5e  sub     r15d, [rdx+38h]
0x140035e62  sub     esi, r15d
0x140035e65  mov     [r8], eax
0x140035e68  cmp     esi, 2
0x140035e6b  jnb     loc_140035F18
0x140035e71  mov     dword ptr [rdi], 1
0x140035e77  mov     r12, [rsp+88h+arg_20]; __annotation("TMF:",
0x140035e7f  lea     r14, WPP_RECORDER_INITIALIZED
0x140035e86  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140035e8d  lea     r13, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140035e94  jz      short loc_140035EBB
0x140035e96  mov     r9d, 0Dh
0x140035e9c  mov     [rsp+88h+var_58], 2
0x140035ea4  mov     dword ptr [rsp+88h+var_60], esi
0x140035ea8  mov     dl, 2
0x140035eaa  mov     rcx, r12
0x140035ead  mov     [rsp+88h+var_68], r13
0x140035eb2  lea     r8d, [r9-8]
0x140035eb6  call    WPP_RECORDER_SF_dD
0x140035ebb  mov     rax, [rbx+18h]
0x140035ebf  mov     edx, 5Ah ; 'Z'
0x140035ec4  mov     rcx, [rbx+28h]
0x140035ec8  call    _guard_dispatch_icall
0x140035ecd  mov     esi, 1
0x140035ed2  cmp     dword ptr [rdi], 0
0x140035ed5  jz      short loc_140035EFC
0x140035ed7  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140035ede  jz      short loc_140035EF9
0x140035ee0  mov     r9d, 12h
0x140035ee6  mov     [rsp+88h+var_68], r13
0x140035eeb  mov     dl, 2
0x140035eed  mov     rcx, r12
0x140035ef0  lea     r8d, [r9-0Dh]
0x140035ef4  call    WPP_RECORDER_SF_
0x140035ef9  xor     sil, sil
0x140035efc  mov     rbx, [rsp+88h+arg_18]
0x140035f04  mov     al, sil
0x140035f07  add     rsp, 50h
0x140035f0b  pop     r15
0x140035f0d  pop     r14
0x140035f0f  pop     r13
0x140035f11  pop     r12
0x140035f13  pop     rdi
0x140035f14  pop     rsi
0x140035f15  pop     rbp
0x140035f16  retn
0x140035f18  movzx   eax, byte ptr [rbp+0]
0x140035f1c  lea     r14, WPP_RECORDER_INITIALIZED
0x140035f23  mov     ecx, [rdx+40h]
0x140035f26  lea     r13, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140035f2d  mov     r12, [rsp+88h+arg_20]
0x140035f35  sub     ecx, ebp
0x140035f37  mov     [rsp+88h+arg_8], ecx
0x140035f3e  mov     [r8], eax
0x140035f41  cmp     eax, esi
0x140035f43  jbe     short loc_140035FA5
0x140035f45  mov     dword ptr [rdi], 2
0x140035f4b  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140035f52  jz      short loc_140035F82
0x140035f54  movzx   eax, byte ptr [rbp+0]
0x140035f58  mov     r9d, 0Eh
0x140035f5e  mov     [rsp+88h+var_48], esi
0x140035f62  mov     dl, 2
0x140035f64  mov     [rsp+88h+var_50], esi
0x140035f68  mov     rcx, r12
0x140035f6b  mov     [rsp+88h+var_58], r15d
0x140035f70  mov     dword ptr [rsp+88h+var_60], eax
0x140035f74  lea     r8d, [r9-9]
0x140035f78  mov     [rsp+88h+var_68], r13
0x140035f7d  call    WPP_RECORDER_SF_DDDD
0x140035f82  mov     rax, [rbx+18h]
0x140035f86  mov     edx, 57h ; 'W'
0x140035f8b  mov     rcx, [rbx+28h]
0x140035f8f  call    _guard_dispatch_icall
0x140035f94  mov     rax, [rsp+88h+arg_10]
0x140035f9c  mov     ecx, [rsp+88h+arg_8]
0x140035fa3  mov     [rax], esi
0x140035fa5  movzx   eax, byte ptr [rbp+0]
0x140035fa9  cmp     eax, ecx
0x140035fab  jbe     short loc_140035FF4
0x140035fad  mov     dword ptr [rdi], 2
0x140035fb3  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140035fba  jz      short loc_140035FE2
0x140035fbc  movzx   eax, byte ptr [rbp+0]
0x140035fc0  mov     r9d, 0Fh
0x140035fc6  mov     [rsp+88h+var_50], ecx
0x140035fca  mov     dl, 2
0x140035fcc  mov     [rsp+88h+var_58], r15d
0x140035fd1  mov     rcx, r12
0x140035fd4  mov     dword ptr [rsp+88h+var_60], eax
0x140035fd8  mov     [rsp+88h+var_68], r13
0x140035fdd  call    WPP_RECORDER_SF_DDD
0x140035fe2  mov     rax, [rbx+18h]
0x140035fe6  mov     edx, 58h ; 'X'
0x140035feb  mov     rcx, [rbx+28h]
0x140035fef  call    _guard_dispatch_icall
0x140035ff4  cmp     byte ptr [rbp+0], 2
0x140035ff8  mov     esi, 200h
0x140035ffd  jnb     short loc_140036055
0x140035fff  cmp     [rbx], si
0x140036002  ja      short loc_14003600A
0x140036004  cmp     byte ptr [rbx+0Ch], 0
0x140036008  jz      short loc_140036010
0x14003600a  mov     dword ptr [rdi], 2
0x140036010  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140036017  jz      short loc_140036043
0x140036019  movzx   eax, byte ptr [rbp+0]
0x14003601d  mov     r9d, 10h
0x140036023  mov     [rsp+88h+var_50], 2
0x14003602b  mov     dl, 2
0x14003602d  mov     [rsp+88h+var_58], r15d
0x140036032  mov     rcx, r12
0x140036035  mov     dword ptr [rsp+88h+var_60], eax
0x140036039  mov     [rsp+88h+var_68], r13
0x14003603e  call    WPP_RECORDER_SF_DDD
0x140036043  mov     rax, [rbx+18h]
0x140036047  mov     edx, 59h ; 'Y'
0x14003604c  mov     rcx, [rbx+28h]
0x140036050  call    _guard_dispatch_icall
0x140036055  cmp     byte ptr [rbp+0], 0
0x140036059  jnz     loc_140035ECD
0x14003605f  cmp     [rbx], si
0x140036062  ja      short loc_14003606A
0x140036064  cmp     byte ptr [rbx+0Ch], 0
0x140036068  jz      short loc_140036073
0x14003606a  mov     esi, 1
0x14003606f  mov     [rdi], esi
0x140036071  jmp     short loc_140036078
0x140036073  mov     esi, 1
0x140036078  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14003607f  jz      short loc_14003609F
0x140036081  mov     r9d, 11h
0x140036087  mov     dword ptr [rsp+88h+var_60], r15d
0x14003608c  mov     dl, 2
0x14003608e  mov     [rsp+88h+var_68], r13
0x140036093  mov     rcx, r12
0x140036096  lea     r8d, [r9-0Ch]
0x14003609a  call    WPP_RECORDER_SF_d
0x14003609f  mov     rax, [rbx+18h]
0x1400360a3  mov     edx, 5Bh ; '['
0x1400360a8  mov     rcx, [rbx+28h]
0x1400360ac  call    _guard_dispatch_icall
0x1400360b1  jmp     loc_140035ED2
```
