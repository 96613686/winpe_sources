# HUBDESC_InternalValidateDeviceCapabilityDescriptor

- ea: `0x14003676c`
- end: `0x140036c7e`
- name: `HUBDESC_InternalValidateDeviceCapabilityDescriptor`
- size: `1298`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x14003c828`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x14001cf04`
- `0x14002d940`
- `0x140035b7c`
- `0x140036468`
- `0x14003676c`
- `0x140037de0`
- `0x1400390e4`
- `0x1400396b0`
- `0x140039cd0`
- `0x14003ad18`
- `0x14003b9a8`
- `0x140045570`

## pseudocode

```c
char __fastcall HUBDESC_InternalValidateDeviceCapabilityDescriptor(
        unsigned __int8 *a1,
        __int64 a2,
        unsigned int *a3,
        int *a4,
        _WORD *a5,
        _WORD *a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  int *v11; // rdi
  __int64 v16; // rdx
  unsigned int v17; // eax
  int v18; // ecx
  char v19; // r12
  int v20; // r8d
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  unsigned __int8 **v26; // rax
  int v28; // [rsp+50h] [rbp-58h] BYREF
  unsigned int v29; // [rsp+B0h] [rbp+8h]
  char v30; // [rsp+D0h] [rbp+28h]

  v11 = a4;
  v28 = 0;
  if ( a4 )
  {
    if ( *(_BYTE *)(a2 + 48) )
      *a4 = 0;
  }
  else
  {
    v11 = &v28;
  }
  if ( a5 )
    *a5 = 0;
  v16 = (__int64)a6;
  if ( a6 )
    *a6 = 0;
  v17 = *a1;
  v18 = (_DWORD)a1 - *(_DWORD *)(a2 + 56);
  v19 = 1;
  *a3 = v17;
  v30 = v18;
  v29 = *(_DWORD *)(a2 + 72) - v18;
  if ( (unsigned __int8)v17 >= 3u )
  {
    if ( (unsigned int)(*(_DWORD *)(a2 + 72) - v18) < 3 )
    {
      if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) )
        *v11 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v16) = 2;
        WPP_RECORDER_SF_d(a11, v16, 5, 228, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v18);
      }
      (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 73);
      goto LABEL_66;
    }
LABEL_14:
    if ( a1[2] == 2 )
    {
      HUBDESC_InternalValidateUSB20DeviceCapabilityDescriptor((_DWORD)a1, a2, (_DWORD)a3, (_DWORD)v11, a8, a11);
      if ( *v11 == 1 )
        goto LABEL_66;
      v26 = *(unsigned __int8 ***)(a2 + 80);
      if ( !*v26 )
      {
        *v26 = a1;
        goto LABEL_66;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v16) = 2;
        WPP_RECORDER_SF_(a11, v16, 5, 229, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
      }
      v22 = 76;
      goto LABEL_37;
    }
    if ( a1[2] == 3 )
    {
      HUBDESC_InternalValidateSuperSpeedDeviceCapabilityDescriptor(
        (_DWORD)a1,
        a2,
        (_DWORD)a3,
        (_DWORD)v11,
        (__int64)a5,
        v16,
        a7,
        a11);
      if ( *v11 == 1 )
        goto LABEL_66;
      v25 = *(_QWORD *)(a2 + 80);
      if ( !*(_QWORD *)(v25 + 8) )
      {
        *(_QWORD *)(v25 + 8) = a1;
        goto LABEL_66;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v16) = 2;
        WPP_RECORDER_SF_(a11, v16, 5, 230, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
      }
      v22 = 75;
      goto LABEL_37;
    }
    if ( a1[2] != 4 )
    {
      if ( a1[2] == 5 )
      {
        HUBDESC_InternalValidatePlatformCapabilityDescriptor((_DWORD)a1, a2, (_DWORD)a3, (_DWORD)v11, a11);
        goto LABEL_66;
      }
      if ( a1[2] == 6 )
      {
        HUBDESC_InternalValidatePowerDeliveryCapabilityDescriptor((_DWORD)a1, a2, (_DWORD)a3, (_DWORD)v11, a11);
        goto LABEL_66;
      }
      if ( a1[2] == 10 )
      {
        HUBDESC_InternalValidateSuperSpeedPlusDeviceCapabilityDescriptor(a1, a2, a3, v11, a11);
        if ( *v11 == 1 )
          goto LABEL_66;
        v23 = *(_QWORD *)(a2 + 80);
        if ( !*(_QWORD *)(v23 + 16) )
        {
          *(_QWORD *)(v23 + 16) = a1;
          goto LABEL_66;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v16) = 2;
          WPP_RECORDER_SF_(a11, v16, 5, 231, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
        }
        v22 = 203;
      }
      else
      {
        if ( a1[2] != 13 )
        {
          if ( a1[2] == 17 )
            HUBDESC_InternalValidateFirmwareStatusCapabilityDescriptor(
              (_DWORD)a1,
              a2,
              (_DWORD)a3,
              (_DWORD)v11,
              a9,
              a10,
              a11);
          goto LABEL_66;
        }
        HUBDESC_InternalValidateBillboardCapabilityDescriptor((_DWORD)a1, a2, (_DWORD)a3, (_DWORD)v11, a11);
        if ( *v11 == 1 )
          goto LABEL_66;
        v21 = *(_QWORD *)(a2 + 80);
        if ( !*(_QWORD *)(v21 + 32) )
        {
          *(_QWORD *)(v21 + 32) = a1;
          goto LABEL_66;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v16) = 2;
          WPP_RECORDER_SF_(a11, v16, 5, 233, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
        }
        v22 = 245;
      }
      goto LABEL_37;
    }
    HUBDESC_InternalValidateContainerIDCapabilityDescriptor((_DWORD)a1, a2, (_DWORD)a3, (_DWORD)v11, a11);
    if ( *v11 == 1 )
      goto LABEL_66;
    v24 = *(_QWORD *)(a2 + 80);
    if ( *(_QWORD *)(v24 + 24) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v16) = 2;
        WPP_RECORDER_SF_(a11, v16, 5, 232, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
      }
      v22 = 74;
LABEL_37:
      (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), v22);
      *v11 = 2;
      goto LABEL_67;
    }
    if ( !*(_BYTE *)(v24 + 41) )
      *(_QWORD *)(v24 + 24) = a1;
LABEL_66:
    if ( !*v11 )
      return v19;
    goto LABEL_67;
  }
  (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 72);
  if ( v29 >= 3 )
  {
    *v11 = 2;
    *a3 = 3;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = 2;
      WPP_RECORDER_SF_DDDD(a11, v16, 5, 226, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v30, *a1, 3, 3);
    }
    v16 = (__int64)a6;
    goto LABEL_14;
  }
  *v11 = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v16) = 2;
    WPP_RECORDER_SF_DDD(a11, v16, v20, 227, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v30, *a1, 3);
    goto LABEL_66;
  }
LABEL_67:
  v19 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v16) = 2;
    WPP_RECORDER_SF_(a11, v16, 5, 234, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  }
  return v19;
}

```

## disassembly

```asm
0x14003676c  push    rbx
0x14003676e  push    rbp
0x14003676f  push    rsi
0x140036770  push    rdi
0x140036771  push    r12
0x140036773  push    r13
0x140036775  push    r14
0x140036777  push    r15
0x140036779  sub     rsp, 68h
0x14003677d  mov     rdi, r9
0x140036780  mov     r15, r8
0x140036783  xor     r9d, r9d
0x140036786  mov     rbx, rdx
0x140036789  mov     [rsp+0A8h+var_58], r9d
0x14003678e  mov     rsi, rcx
0x140036791  test    rdi, rdi
0x140036794  jnz     short loc_14003679D
0x140036796  lea     rdi, [rsp+0A8h+var_58]
0x14003679b  jmp     short loc_1400367A6
0x14003679d  cmp     [rdx+30h], r9b
0x1400367a1  jz      short loc_1400367A6
0x1400367a3  mov     [rdi], r9d
0x1400367a6  mov     r13, [rsp+0A8h+arg_20]
0x1400367ae  test    r13, r13
0x1400367b1  jz      short loc_1400367B8
0x1400367b3  mov     [r13+0], r9w
0x1400367b8  mov     rdx, [rsp+0A8h+arg_28]
0x1400367c0  test    rdx, rdx
0x1400367c3  jz      short loc_1400367C9
0x1400367c5  mov     [rdx], r9w
0x1400367c9  movzx   eax, byte ptr [rcx]
0x1400367cc  lea     r11, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x1400367d3  sub     ecx, [rbx+38h]
0x1400367d6  lea     r14, WPP_RECORDER_INITIALIZED
0x1400367dd  mov     rbp, [rsp+0A8h+arg_50]
0x1400367e5  mov     r12d, 1
0x1400367eb  mov     [r8], eax
0x1400367ee  mov     r8d, [rbx+48h]
0x1400367f2  sub     r8d, ecx
0x1400367f5  mov     dword ptr [rsp+0A8h+arg_20], ecx
0x1400367fc  lea     r10d, [r12+2]
0x140036801  mov     [rsp+0A8h+arg_0], r8d
0x140036809  cmp     al, r10b
0x14003680c  jnb     loc_140036963
0x140036812  mov     rax, [rbx+18h]
0x140036816  lea     edx, [r12+47h]
0x14003681b  mov     rcx, [rbx+28h]
0x14003681f  call    _guard_dispatch_icall
0x140036824  lea     r10d, [r12+2]
0x140036829  cmp     [rsp+0A8h+arg_0], r10d
0x140036831  jb      loc_140036914
0x140036837  mov     dword ptr [rdi], 2
0x14003683d  mov     [r15], r10d
0x140036840  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140036847  jz      short loc_14003688B
0x140036849  movzx   eax, byte ptr [rsi]
0x14003684c  lea     r8d, [r12+4]
0x140036851  mov     [rsp+0A8h+var_68], r10d
0x140036856  mov     r9d, 0E2h
0x14003685c  mov     dword ptr [rsp+0A8h+var_70], r10d
0x140036861  mov     dl, 2
0x140036863  mov     dword ptr [rsp+0A8h+var_78], eax
0x140036867  mov     rcx, rbp
0x14003686a  mov     eax, dword ptr [rsp+0A8h+arg_20]
0x140036871  mov     dword ptr [rsp+0A8h+var_80], eax
0x140036875  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003687c  mov     [rsp+0A8h+var_88], rax
0x140036881  call    WPP_RECORDER_SF_DDDD
0x140036886  lea     r10d, [r12+2]
0x14003688b  mov     rdx, [rsp+0A8h+arg_28]
0x140036893  movzx   ecx, byte ptr [rsi+2]
0x140036897  sub     ecx, 2
0x14003689a  jz      loc_140036BCC
0x1400368a0  sub     ecx, r12d
0x1400368a3  jz      loc_140036B50
0x1400368a9  sub     ecx, r12d
0x1400368ac  jz      loc_140036ADE
0x1400368b2  sub     ecx, r12d
0x1400368b5  jz      loc_140036AC3
0x1400368bb  sub     ecx, r12d
0x1400368be  jz      loc_140036AA8
0x1400368c4  sub     ecx, 4
0x1400368c7  jz      loc_140036A43
0x1400368cd  sub     ecx, r10d
0x1400368d0  jz      loc_1400369C8
0x1400368d6  cmp     ecx, 4
0x1400368d9  jnz     loc_140036C36
0x1400368df  mov     rax, [rsp+0A8h+arg_48]
0x1400368e7  mov     r9, rdi
0x1400368ea  mov     [rsp+0A8h+var_78], rbp
0x1400368ef  mov     r8, r15
0x1400368f2  mov     [rsp+0A8h+var_80], rax
0x1400368f7  mov     rdx, rbx
0x1400368fa  mov     rax, [rsp+0A8h+arg_40]
0x140036902  mov     rcx, rsi
0x140036905  mov     [rsp+0A8h+var_88], rax
0x14003690a  call    HUBDESC_InternalValidateFirmwareStatusCapabilityDescriptor
0x14003690f  jmp     loc_140036C36
0x140036914  mov     [rdi], r12d
0x140036917  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003691e  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140036925  jz      loc_140036C3B
0x14003692b  movzx   eax, byte ptr [rsi]
0x14003692e  mov     r9d, 0E3h
0x140036934  mov     dword ptr [rsp+0A8h+var_70], r10d
0x140036939  mov     dl, 2
0x14003693b  mov     dword ptr [rsp+0A8h+var_78], eax
0x14003693f  mov     rcx, rbp
0x140036942  mov     eax, dword ptr [rsp+0A8h+arg_20]
0x140036949  mov     dword ptr [rsp+0A8h+var_80], eax
0x14003694d  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140036954  mov     [rsp+0A8h+var_88], rax
0x140036959  call    WPP_RECORDER_SF_DDD
0x14003695e  jmp     loc_140036C36
0x140036963  cmp     r8d, r10d
0x140036966  jnb     loc_140036893
0x14003696c  mov     eax, 200h
0x140036971  cmp     [rbx], ax
0x140036974  ja      short loc_14003697C
0x140036976  cmp     [rbx+0Ch], r9b
0x14003697a  jz      short loc_140036982
0x14003697c  mov     dword ptr [rdi], 2
0x140036982  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140036989  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140036990  jz      short loc_1400369B1
0x140036992  mov     dword ptr [rsp+0A8h+var_80], ecx
0x140036996  mov     r9d, 0E4h
0x14003699c  mov     rcx, rbp
0x14003699f  mov     [rsp+0A8h+var_88], r11
0x1400369a4  mov     r8d, 5
0x1400369aa  mov     dl, 2
0x1400369ac  call    WPP_RECORDER_SF_d
0x1400369b1  mov     rax, [rbx+18h]
0x1400369b5  mov     edx, 49h ; 'I'
0x1400369ba  mov     rcx, [rbx+28h]
0x1400369be  call    _guard_dispatch_icall
0x1400369c3  jmp     loc_140036C36
0x1400369c8  mov     r9, rdi
0x1400369cb  mov     [rsp+0A8h+var_88], rbp
0x1400369d0  mov     r8, r15
0x1400369d3  mov     rdx, rbx
0x1400369d6  mov     rcx, rsi
0x1400369d9  call    HUBDESC_InternalValidateBillboardCapabilityDescriptor
0x1400369de  cmp     [rdi], r12d
0x1400369e1  jz      loc_140036C36
0x1400369e7  mov     rax, [rbx+50h]
0x1400369eb  cmp     qword ptr [rax+20h], 0
0x1400369f0  jz      short loc_140036A3A
0x1400369f2  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400369f9  jz      short loc_140036A1D
0x1400369fb  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140036a02  mov     r9d, 0E9h
0x140036a08  mov     r8d, 5
0x140036a0e  mov     [rsp+0A8h+var_88], rax
0x140036a13  mov     dl, 2
0x140036a15  mov     rcx, rbp
0x140036a18  call    WPP_RECORDER_SF_
0x140036a1d  mov     edx, 0F5h
0x140036a22  mov     rax, [rbx+18h]
0x140036a26  mov     rcx, [rbx+28h]
0x140036a2a  call    _guard_dispatch_icall
0x140036a2f  mov     dword ptr [rdi], 2
0x140036a35  jmp     loc_140036C3B
0x140036a3a  mov     [rax+20h], rsi
0x140036a3e  jmp     loc_140036C36
0x140036a43  mov     r9, rdi
0x140036a46  mov     [rsp+0A8h+var_88], rbp
0x140036a4b  mov     r8, r15
0x140036a4e  mov     rdx, rbx
0x140036a51  mov     rcx, rsi
0x140036a54  call    HUBDESC_InternalValidateSuperSpeedPlusDeviceCapabilityDescriptor
0x140036a59  cmp     [rdi], r12d
0x140036a5c  jz      loc_140036C36
0x140036a62  mov     rax, [rbx+50h]
0x140036a66  cmp     qword ptr [rax+10h], 0
0x140036a6b  jz      short loc_140036A9F
0x140036a6d  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140036a74  jz      short loc_140036A98
0x140036a76  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140036a7d  mov     r9d, 0E7h
0x140036a83  mov     r8d, 5
0x140036a89  mov     [rsp+0A8h+var_88], rax
0x140036a8e  mov     dl, 2
0x140036a90  mov     rcx, rbp
0x140036a93  call    WPP_RECORDER_SF_
0x140036a98  mov     edx, 0CBh
0x140036a9d  jmp     short loc_140036A22
0x140036a9f  mov     [rax+10h], rsi
0x140036aa3  jmp     loc_140036C36
0x140036aa8  mov     r9, rdi
0x140036aab  mov     [rsp+0A8h+var_88], rbp
0x140036ab0  mov     r8, r15
0x140036ab3  mov     rdx, rbx
0x140036ab6  mov     rcx, rsi
0x140036ab9  call    HUBDESC_InternalValidatePowerDeliveryCapabilityDescriptor
0x140036abe  jmp     loc_140036C36
0x140036ac3  mov     r9, rdi
0x140036ac6  mov     [rsp+0A8h+var_88], rbp
0x140036acb  mov     r8, r15
0x140036ace  mov     rdx, rbx
0x140036ad1  mov     rcx, rsi
0x140036ad4  call    HUBDESC_InternalValidatePlatformCapabilityDescriptor
0x140036ad9  jmp     loc_140036C36
0x140036ade  mov     r9, rdi
0x140036ae1  mov     [rsp+0A8h+var_88], rbp
0x140036ae6  mov     r8, r15
0x140036ae9  mov     rdx, rbx
0x140036aec  mov     rcx, rsi
0x140036aef  call    HUBDESC_InternalValidateContainerIDCapabilityDescriptor
0x140036af4  cmp     [rdi], r12d
0x140036af7  jz      loc_140036C36
0x140036afd  mov     rax, [rbx+50h]
0x140036b01  cmp     qword ptr [rax+18h], 0
0x140036b06  jz      short loc_140036B3D
0x140036b08  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140036b0f  jz      short loc_140036B33
0x140036b11  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140036b18  mov     r9d, 0E8h
0x140036b1e  mov     r8d, 5
0x140036b24  mov     [rsp+0A8h+var_88], rax
0x140036b29  mov     dl, 2
0x140036b2b  mov     rcx, rbp
0x140036b2e  call    WPP_RECORDER_SF_
0x140036b33  mov     edx, 4Ah ; 'J'
0x140036b38  jmp     loc_140036A22
0x140036b3d  cmp     byte ptr [rax+29h], 0
0x140036b41  jnz     loc_140036C36
0x140036b47  mov     [rax+18h], rsi
0x140036b4b  jmp     loc_140036C36
0x140036b50  mov     rax, [rsp+0A8h+arg_30]
0x140036b58  mov     r9, rdi
0x140036b5b  mov     [rsp+0A8h+var_70], rbp
0x140036b60  mov     r8, r15
0x140036b63  mov     [rsp+0A8h+var_78], rax
0x140036b68  mov     rcx, rsi
0x140036b6b  mov     [rsp+0A8h+var_80], rdx
0x140036b70  mov     rdx, rbx
0x140036b73  mov     [rsp+0A8h+var_88], r13
0x140036b78  call    HUBDESC_InternalValidateSuperSpeedDeviceCapabilityDescriptor
0x140036b7d  cmp     [rdi], r12d
0x140036b80  jz      loc_140036C36
0x140036b86  mov     rax, [rbx+50h]
0x140036b8a  cmp     qword ptr [rax+8], 0
0x140036b8f  jz      short loc_140036BC6
0x140036b91  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140036b98  jz      short loc_140036BBC
0x140036b9a  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140036ba1  mov     r9d, 0E6h
0x140036ba7  mov     r8d, 5
0x140036bad  mov     [rsp+0A8h+var_88], rax
0x140036bb2  mov     dl, 2
0x140036bb4  mov     rcx, rbp
0x140036bb7  call    WPP_RECORDER_SF_
0x140036bbc  mov     edx, 4Bh ; 'K'
0x140036bc1  jmp     loc_140036A22
0x140036bc6  mov     [rax+8], rsi
0x140036bca  jmp     short loc_140036C36
0x140036bcc  mov     rax, [rsp+0A8h+arg_38]
0x140036bd4  mov     r9, rdi
0x140036bd7  mov     [rsp+0A8h+var_80], rbp
0x140036bdc  mov     r8, r15
0x140036bdf  mov     rdx, rbx
0x140036be2  mov     [rsp+0A8h+var_88], rax
0x140036be7  mov     rcx, rsi
0x140036bea  call    HUBDESC_InternalValidateUSB20DeviceCapabilityDescriptor
0x140036bef  cmp     [rdi], r12d
0x140036bf2  jz      short loc_140036C36
0x140036bf4  mov     rax, [rbx+50h]
0x140036bf8  cmp     qword ptr [rax], 0
0x140036bfc  jz      short loc_140036C33
0x140036bfe  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140036c05  jz      short loc_140036C29
0x140036c07  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140036c0e  mov     r9d, 0E5h
0x140036c14  mov     r8d, 5
0x140036c1a  mov     [rsp+0A8h+var_88], rax
0x140036c1f  mov     dl, 2
0x140036c21  mov     rcx, rbp
0x140036c24  call    WPP_RECORDER_SF_
0x140036c29  mov     edx, 4Ch ; 'L'
0x140036c2e  jmp     loc_140036A22
0x140036c33  mov     [rax], rsi
0x140036c36  cmp     dword ptr [rdi], 0
0x140036c39  jz      short loc_140036C69
0x140036c3b  xor     r12b, r12b
0x140036c3e  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140036c45  jz      short loc_140036C69
0x140036c47  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140036c4e  mov     r9d, 0EAh
0x140036c54  mov     r8d, 5
0x140036c5a  mov     [rsp+0A8h+var_88], rax
0x140036c5f  mov     dl, 2
0x140036c61  mov     rcx, rbp
0x140036c64  call    WPP_RECORDER_SF_
0x140036c69  mov     al, r12b
0x140036c6c  add     rsp, 68h
0x140036c70  pop     r15
0x140036c72  pop     r14
0x140036c74  pop     r13
0x140036c76  pop     r12
  ... truncated ...
```
