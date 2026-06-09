# HUBDESC_InternalValidateBOSDescriptor

- ea: `0x1400357e0`
- end: `0x140035b76`
- name: `HUBDESC_InternalValidateBOSDescriptor`
- size: `918`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14002c0b8`
- `0x14003c828`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x1400067ac`
- `0x1400357e0`
- `0x14003bf54`
- `0x14003f208`
- `0x140045570`

## pseudocode

```c
char __fastcall HUBDESC_InternalValidateBOSDescriptor(unsigned __int8 *a1, __int64 a2, _DWORD *a3, int *a4, __int64 a5)
{
  int *v5; // rdi
  int v9; // edx
  char v10; // r13
  int v11; // r15d
  __int64 v12; // rdx
  __int64 v13; // rax
  unsigned int v14; // edx
  unsigned int v15; // eax
  int v16; // edx
  int v17; // r8d
  int v19; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v20; // [rsp+80h] [rbp+18h]

  v5 = a4;
  v19 = 0;
  if ( a4 )
  {
    if ( *(_BYTE *)(a2 + 48) )
      *a4 = 0;
  }
  else
  {
    v5 = &v19;
  }
  v9 = 5;
  if ( a3 )
    *a3 = 5;
  v10 = 1;
  if ( !a1 )
  {
    *v5 = 1;
    v11 = a5;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_(a5, v9, 5, 235, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
    }
    v12 = 27;
LABEL_48:
    (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), v12);
    goto LABEL_49;
  }
  v11 = a5;
  if ( *(_DWORD *)(a2 + 72) < 5u )
  {
    *v5 = 1;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_dD(
        v11,
        v9,
        5,
        236,
        (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
        *(_DWORD *)(a2 + 72),
        5);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 23);
    v9 = 5;
  }
  if ( a1[1] != 15 )
  {
    *v5 = 2;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_dD(v11, v9, 5, 237, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, a1[1], 15);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 24);
  }
  if ( *a1 < 5u )
  {
    *v5 = 2;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Ddd(v11, v9, (_DWORD)a3, 238);
    (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 21);
  }
  v13 = *((unsigned __int16 *)a1 + 1);
  if ( (unsigned int)v13 < *(_DWORD *)(a2 + 72) )
    *(_QWORD *)(a2 + 64) = *(_QWORD *)(a2 + 56) + v13;
  if ( *a1 > 5u )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Ddd(v11, v9, (_DWORD)a3, 239);
    (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 20);
    if ( (unsigned __int8)HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
      *v5 = 2;
    if ( a3 )
      *a3 = *a1;
  }
  if ( *((_WORD *)a1 + 1) < 5u )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_d(v11, v9, 5, 240, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, *((_WORD *)a1 + 1));
    }
    (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 29);
    *(_QWORD *)(a2 + 64) = *(_QWORD *)(a2 + 56) + *(unsigned int *)(a2 + 72);
    *v5 = 2;
  }
  v14 = *a1 + 2 * a1[4];
  v15 = *((unsigned __int16 *)a1 + 1);
  v20 = v14;
  if ( v15 < v14 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Ddd(v11, v14, (_DWORD)a3, 241);
    (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 29);
    *(_QWORD *)(a2 + 64) = *(_QWORD *)(a2 + 56) + *(unsigned int *)(a2 + 72);
    *v5 = 2;
  }
  if ( !a1[4] )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_(v11, v14, 5, 242, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
    }
    if ( (unsigned __int8)HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
      *v5 = 2;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Ddd(v11, v16, v17, 243);
    v12 = 29;
    goto LABEL_48;
  }
LABEL_49:
  if ( *v5 )
  {
    v10 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_(v11, v14, 5, 244, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1400357e0  mov     [rsp+arg_8], rbx
0x1400357e5  mov     [rsp+arg_18], rsi
0x1400357ea  push    rdi
0x1400357eb  push    r12
0x1400357ed  push    r13
0x1400357ef  push    r14
0x1400357f1  push    r15
0x1400357f3  sub     rsp, 40h
0x1400357f7  xor     eax, eax
0x1400357f9  mov     rdi, r9
0x1400357fc  mov     [rsp+68h+arg_0], eax
0x140035800  mov     r12, r8
0x140035803  mov     rbx, rdx
0x140035806  mov     rsi, rcx
0x140035809  test    r9, r9
0x14003580c  jnz     short loc_140035815
0x14003580e  lea     rdi, [rsp+68h+arg_0]
0x140035813  jmp     short loc_14003581D
0x140035815  cmp     [rdx+30h], al
0x140035818  jz      short loc_14003581D
0x14003581a  mov     [r9], eax
0x14003581d  mov     edx, 5
0x140035822  test    r12, r12
0x140035825  jz      short loc_14003582A
0x140035827  mov     [r8], edx
0x14003582a  mov     r13d, 1
0x140035830  test    rsi, rsi
0x140035833  jnz     short loc_140035879
0x140035835  mov     [rdi], r13d
0x140035838  mov     r15, [rsp+68h+arg_20]; __annotation("TMF:",
0x140035840  lea     r14, WPP_RECORDER_INITIALIZED
0x140035847  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14003584e  lea     r12, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140035855  jz      short loc_14003586F
0x140035857  mov     r8d, edx
0x14003585a  mov     [rsp+68h+var_48], r12
0x14003585f  mov     dl, 2
0x140035861  mov     r9d, 0EBh
0x140035867  mov     rcx, r15
0x14003586a  call    WPP_RECORDER_SF_
0x14003586f  mov     edx, 1Bh
0x140035874  jmp     loc_140035B1F
0x140035879  lea     r14, WPP_RECORDER_INITIALIZED
0x140035880  mov     r15, [rsp+68h+arg_20]
0x140035888  lea     rcx, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003588f  cmp     [rbx+48h], edx
0x140035892  jnb     short loc_1400358E1
0x140035894  mov     [rdi], r13d
0x140035897  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14003589e  jz      short loc_1400358C3
0x1400358a0  mov     eax, [rbx+48h]
0x1400358a3  mov     r8d, edx
0x1400358a6  mov     [rsp+68h+var_38], edx
0x1400358aa  mov     r9d, 0ECh
0x1400358b0  mov     [rsp+68h+var_40], eax
0x1400358b4  mov     dl, 2
0x1400358b6  mov     [rsp+68h+var_48], rcx
0x1400358bb  mov     rcx, r15
0x1400358be  call    WPP_RECORDER_SF_dD
0x1400358c3  mov     rax, [rbx+18h]
0x1400358c7  mov     edx, 17h
0x1400358cc  mov     rcx, [rbx+28h]
0x1400358d0  call    _guard_dispatch_icall
0x1400358d5  lea     rcx, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x1400358dc  mov     edx, 5
0x1400358e1  cmp     byte ptr [rsi+1], 0Fh
0x1400358e5  jz      short loc_140035930
0x1400358e7  mov     dword ptr [rdi], 2
0x1400358ed  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400358f4  jz      short loc_14003591E
0x1400358f6  movzx   eax, byte ptr [rsi+1]
0x1400358fa  mov     r8d, edx
0x1400358fd  mov     [rsp+68h+var_38], 0Fh
0x140035905  mov     r9d, 0EDh
0x14003590b  mov     [rsp+68h+var_40], eax
0x14003590f  mov     dl, 2
0x140035911  mov     [rsp+68h+var_48], rcx
0x140035916  mov     rcx, r15
0x140035919  call    WPP_RECORDER_SF_dD
0x14003591e  mov     rax, [rbx+18h]
0x140035922  mov     edx, 18h
0x140035927  mov     rcx, [rbx+28h]
0x14003592b  call    _guard_dispatch_icall
0x140035930  mov     ecx, 5
0x140035935  cmp     [rsi], cl
0x140035937  jnb     short loc_14003597C
0x140035939  mov     dword ptr [rdi], 2
0x14003593f  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140035946  jz      short loc_140035965
0x140035948  movzx   eax, byte ptr [rsi]
0x14003594b  mov     r9d, 0EEh
0x140035951  mov     [rsp+68h+var_30], ecx
0x140035955  mov     [rsp+68h+var_38], ecx
0x140035959  mov     rcx, r15
0x14003595c  mov     [rsp+68h+var_40], eax
0x140035960  call    WPP_RECORDER_SF_Ddd
0x140035965  mov     rax, [rbx+18h]
0x140035969  mov     edx, 15h
0x14003596e  mov     rcx, [rbx+28h]
0x140035972  call    _guard_dispatch_icall
0x140035977  mov     ecx, 5
0x14003597c  movzx   eax, word ptr [rsi+2]
0x140035980  cmp     eax, [rbx+48h]
0x140035983  jnb     short loc_14003598D
0x140035985  add     rax, [rbx+38h]
0x140035989  mov     [rbx+40h], rax
0x14003598d  movzx   eax, byte ptr [rsi]
0x140035990  cmp     al, cl
0x140035992  jbe     short loc_1400359EC
0x140035994  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14003599b  jz      short loc_1400359B7
0x14003599d  mov     [rsp+68h+var_30], eax
0x1400359a1  mov     r9d, 0EFh
0x1400359a7  mov     [rsp+68h+var_38], ecx
0x1400359ab  mov     rcx, r15
0x1400359ae  mov     [rsp+68h+var_40], eax
0x1400359b2  call    WPP_RECORDER_SF_Ddd
0x1400359b7  mov     rax, [rbx+18h]
0x1400359bb  mov     edx, 14h
0x1400359c0  mov     rcx, [rbx+28h]
0x1400359c4  call    _guard_dispatch_icall
0x1400359c9  mov     rcx, rbx
0x1400359cc  call    HUBDESC_ShouldEnforceWin8ValidationMutable
0x1400359d1  test    al, al
0x1400359d3  jz      short loc_1400359DB
0x1400359d5  mov     dword ptr [rdi], 2
0x1400359db  mov     ecx, 5
0x1400359e0  test    r12, r12
0x1400359e3  jz      short loc_1400359EC
0x1400359e5  movzx   eax, byte ptr [rsi]
0x1400359e8  mov     [r12], eax
0x1400359ec  movzx   eax, word ptr [rsi+2]
0x1400359f0  cmp     ax, cx
0x1400359f3  jnb     short loc_140035A46
0x1400359f5  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400359fc  lea     r12, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140035a03  jz      short loc_140035A21
0x140035a05  mov     r8d, ecx
0x140035a08  mov     [rsp+68h+var_40], eax
0x140035a0c  mov     rcx, r15
0x140035a0f  mov     [rsp+68h+var_48], r12
0x140035a14  mov     r9d, 0F0h
0x140035a1a  mov     dl, 2
0x140035a1c  call    WPP_RECORDER_SF_d
0x140035a21  mov     rax, [rbx+18h]
0x140035a25  mov     edx, 1Dh
0x140035a2a  mov     rcx, [rbx+28h]
0x140035a2e  call    _guard_dispatch_icall
0x140035a33  mov     eax, [rbx+48h]
0x140035a36  add     rax, [rbx+38h]
0x140035a3a  mov     [rbx+40h], rax
0x140035a3e  mov     dword ptr [rdi], 2
0x140035a44  jmp     short loc_140035A4D
0x140035a46  lea     r12, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140035a4d  movzx   eax, byte ptr [rsi]
0x140035a50  movzx   ecx, byte ptr [rsi+4]
0x140035a54  lea     edx, [rax+rcx*2]
0x140035a57  movzx   eax, word ptr [rsi+2]
0x140035a5b  mov     [rsp+68h+arg_10], edx
0x140035a62  cmp     eax, edx
0x140035a64  jnb     short loc_140035AAC
0x140035a66  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140035a6d  jz      short loc_140035A89
0x140035a6f  mov     [rsp+68h+var_30], ecx
0x140035a73  mov     r9d, 0F1h
0x140035a79  mov     [rsp+68h+var_38], edx
0x140035a7d  mov     rcx, r15
0x140035a80  mov     [rsp+68h+var_40], eax
0x140035a84  call    WPP_RECORDER_SF_Ddd
0x140035a89  mov     rax, [rbx+18h]
0x140035a8d  mov     edx, 1Dh
0x140035a92  mov     rcx, [rbx+28h]
0x140035a96  call    _guard_dispatch_icall
0x140035a9b  mov     eax, [rbx+48h]
0x140035a9e  add     rax, [rbx+38h]
0x140035aa2  mov     [rbx+40h], rax
0x140035aa6  mov     dword ptr [rdi], 2
0x140035aac  cmp     byte ptr [rsi+4], 0
0x140035ab0  jnz     short loc_140035B2C
0x140035ab2  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140035ab9  jz      short loc_140035AD6
0x140035abb  mov     r9d, 0F2h
0x140035ac1  mov     [rsp+68h+var_48], r12
0x140035ac6  mov     r8d, 5
0x140035acc  mov     dl, 2
0x140035ace  mov     rcx, r15
0x140035ad1  call    WPP_RECORDER_SF_
0x140035ad6  mov     rcx, rbx
0x140035ad9  call    HUBDESC_ShouldEnforceWin8ValidationMutable
0x140035ade  test    al, al
0x140035ae0  jz      short loc_140035AE8
0x140035ae2  mov     dword ptr [rdi], 2
0x140035ae8  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140035aef  jz      short loc_140035B1A
0x140035af1  movzx   eax, byte ptr [rsi+4]
0x140035af5  mov     r9d, 0F3h
0x140035afb  movzx   ecx, word ptr [rsi+2]
0x140035aff  mov     [rsp+68h+var_30], eax
0x140035b03  mov     eax, [rsp+68h+arg_10]
0x140035b0a  mov     [rsp+68h+var_38], eax
0x140035b0e  mov     [rsp+68h+var_40], ecx
0x140035b12  mov     rcx, r15
0x140035b15  call    WPP_RECORDER_SF_Ddd
0x140035b1a  mov     edx, 1Dh
0x140035b1f  mov     rcx, [rbx+28h]
0x140035b23  mov     rax, [rbx+18h]
0x140035b27  call    _guard_dispatch_icall
0x140035b2c  cmp     dword ptr [rdi], 0
0x140035b2f  jz      short loc_140035B58
0x140035b31  xor     r13b, r13b
0x140035b34  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140035b3b  jz      short loc_140035B58
0x140035b3d  mov     r9d, 0F4h
0x140035b43  mov     [rsp+68h+var_48], r12
0x140035b48  mov     r8d, 5
0x140035b4e  mov     dl, 2
0x140035b50  mov     rcx, r15
0x140035b53  call    WPP_RECORDER_SF_
0x140035b58  lea     r11, [rsp+68h+var_28]
0x140035b5d  mov     al, r13b
0x140035b60  mov     rbx, [r11+38h]
0x140035b64  mov     rsi, [r11+48h]
0x140035b68  mov     rsp, r11
0x140035b6b  pop     r15
0x140035b6d  pop     r14
0x140035b6f  pop     r13
0x140035b71  pop     r12
0x140035b73  pop     rdi
0x140035b74  retn
```
