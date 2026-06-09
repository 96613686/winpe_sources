# HUBDESC_InternalValidatePlatformCapabilityDescriptor

- ea: `0x1400390e4`
- end: `0x1400396a9`
- name: `HUBDESC_InternalValidatePlatformCapabilityDescriptor`
- size: `1477`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14003676c`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x14001cf04`
- `0x14002d940`
- `0x1400390e4`
- `0x140045570`

## import_xrefs

- `ntoskrnl!RtlIsNtDdiVersionAvailable` at `0x1400394af`
- `ntoskrnl!RtlIsNtDdiVersionAvailable` at `0x1400394af`

## pseudocode

```c
char __fastcall HUBDESC_InternalValidatePlatformCapabilityDescriptor(
        unsigned __int8 *a1,
        __int64 a2,
        unsigned int *a3,
        int *a4,
        __int64 a5)
{
  int *v5; // rsi
  unsigned int *v6; // rax
  __int64 v7; // rbx
  int v9; // r15d
  char v10; // bp
  int v11; // r12d
  unsigned int v12; // r13d
  int v13; // r8d
  __int64 v14; // rdx
  int v15; // r9d
  unsigned __int64 v16; // r13
  unsigned int v17; // eax
  bool v18; // zf
  unsigned int v19; // r13d
  __int64 v20; // r12
  __int64 v21; // rdx
  __int64 v22; // r12
  ULONG *v23; // r13
  __int64 v24; // rax
  int v26; // [rsp+28h] [rbp-80h]
  __int64 v27; // [rsp+50h] [rbp-58h]
  unsigned int v28; // [rsp+58h] [rbp-50h]
  ULONG v29; // [rsp+B0h] [rbp+8h]
  int v30; // [rsp+B8h] [rbp+10h] BYREF
  unsigned int *v31; // [rsp+C0h] [rbp+18h]
  unsigned int v32; // [rsp+C8h] [rbp+20h]

  v31 = a3;
  v30 = 0;
  v5 = a4;
  v6 = a3;
  v7 = a2;
  if ( a4 )
  {
    if ( *(_BYTE *)(a2 + 48) )
      *a4 = 0;
  }
  else
  {
    v5 = &v30;
  }
  v9 = a5;
  v10 = 1;
  v11 = (_DWORD)a1 - *(_DWORD *)(a2 + 56);
  v12 = *(_DWORD *)(a2 + 72) - v11;
  if ( *a1 >= 0x14u )
  {
LABEL_9:
    if ( *v6 > v12 )
    {
      if ( *(_WORD *)v7 > 0x200u || *(_BYTE *)(v7 + 12) )
        *v5 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_d(v9, a2, 5, 154, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v11);
      }
      v14 = 253;
      goto LABEL_16;
    }
    if ( a1[3] )
    {
      if ( *(_BYTE *)(v7 + 15) )
        *v5 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_d(v9, a2, 5, 155, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, a1[3]);
      }
      (*(void (__fastcall **)(_QWORD, __int64))(v7 + 24))(*(_QWORD *)(v7 + 40), 195);
    }
    if ( *(_QWORD *)(a1 + 4) == *(_QWORD *)&GUID_NULL.Data1 && *(_QWORD *)(a1 + 12) == *(_QWORD *)GUID_NULL.Data4 )
    {
      *v5 = 1;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_(v9, a2, 5, 156, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
      }
      v14 = 196;
      goto LABEL_16;
    }
    if ( *(_QWORD *)(a1 + 4) == *(_QWORD *)&GUID_USB_MSOS20_PLATFORM_CAPABILITY_ID.Data1
      && *(_QWORD *)(a1 + 12) == *(_QWORD *)GUID_USB_MSOS20_PLATFORM_CAPABILITY_ID.Data4 )
    {
      if ( *(_QWORD *)(*(_QWORD *)(v7 + 80) + 48LL) )
      {
        *v5 = 1;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = 2;
          WPP_RECORDER_SF_(v9, a2, 5, 157, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
        }
        v14 = 197;
        goto LABEL_16;
      }
      if ( *a1 < 0x1Cu )
      {
        *v5 = 1;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_41:
          v14 = 198;
          goto LABEL_16;
        }
        v15 = 158;
LABEL_40:
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_d(v9, a2, 5, v15, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, *a1);
        goto LABEL_41;
      }
      if ( ((*a1 - 4) & 7) != 0 )
      {
        *v5 = 1;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_41;
        v15 = 159;
        goto LABEL_40;
      }
      v29 = 0;
      v16 = ((unsigned __int64)*a1 - 28) >> 3;
      v17 = 0;
      v18 = (_DWORD)v16 == -1;
      v19 = v16 + 1;
      v28 = v19;
      if ( v18 )
        goto LABEL_60;
      while ( 1 )
      {
        v20 = v17 + 1;
        v21 = v17;
        v27 = v17;
        v32 = v20;
        if ( (unsigned int)v20 >= v19 )
          break;
        do
        {
          if ( *(_DWORD *)&a1[8 * v20 + 20] == *(_DWORD *)&a1[8 * v21 + 20] )
          {
            *v5 = 1;
            *(_QWORD *)(*(_QWORD *)(v7 + 80) + 48LL) = 0;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v26 = *(_DWORD *)&a1[8 * v21 + 20];
              LOBYTE(v21) = 2;
              WPP_RECORDER_SF_d(v9, v21, 5, 160, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v26);
            }
            (*(void (__fastcall **)(_QWORD, __int64))(v7 + 24))(*(_QWORD *)(v7 + 40), 199);
            v21 = v27;
          }
          v20 = (unsigned int)(v20 + 1);
        }
        while ( (unsigned int)v20 < v19 );
        v17 = v32;
      }
      v22 = 0;
      LODWORD(a2) = 0;
      do
      {
        v23 = (ULONG *)&a1[8 * v22 + 20];
        if ( *v23 > (unsigned int)a2 )
        {
          if ( RtlIsNtDdiVersionAvailable(*v23) )
          {
            LODWORD(a2) = *v23;
            v29 = *v23;
            *(_QWORD *)(*(_QWORD *)(v7 + 80) + 48LL) = v23;
          }
          else
          {
            LODWORD(a2) = v29;
          }
        }
        v22 = (unsigned int)(v22 + 1);
      }
      while ( (unsigned int)v22 < v28 );
      v9 = a5;
      if ( !(_DWORD)a2 )
      {
LABEL_60:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = 2;
          WPP_RECORDER_SF_(v9, a2, 5, 161, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
        }
        (*(void (__fastcall **)(_QWORD, __int64))(v7 + 32))(*(_QWORD *)(v7 + 40), 200);
      }
    }
    else if ( *(_QWORD *)(a1 + 4) == *(_QWORD *)&GUID_USB_PLATFORM_FEATURES.Data1
           && *(_QWORD *)(a1 + 12) == *(_QWORD *)GUID_USB_PLATFORM_FEATURES.Data4 )
    {
      if ( *a1 >= 0x1Au )
      {
        if ( a1[20] == 1 )
        {
          if ( *a1 != 26 )
          {
            *v5 = 1;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(a2) = 2;
              WPP_RECORDER_SF_d(v9, a2, 5, 163, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, *a1);
            }
            v14 = 247;
            goto LABEL_16;
          }
        }
        else if ( !a1[20] )
        {
          *v5 = 1;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(a2) = 2;
            WPP_RECORDER_SF_d(v9, a2, 5, 164, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, a1[20]);
          }
          v14 = 249;
          goto LABEL_16;
        }
        v24 = *(_QWORD *)(v7 + 80);
        if ( !*(_QWORD *)(v24 + 56) )
        {
          *(_QWORD *)(v24 + 56) = a1;
          goto LABEL_83;
        }
        *v5 = 1;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = 2;
          WPP_RECORDER_SF_(v9, a2, 5, 165, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
        }
        v14 = 248;
        goto LABEL_16;
      }
      *v5 = 1;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_d(v9, a2, 5, 162, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, *a1);
      }
      v14 = 250;
LABEL_16:
      (*(void (__fastcall **)(_QWORD, __int64))(v7 + 24))(*(_QWORD *)(v7 + 40), v14);
    }
LABEL_83:
    if ( !*v5 )
      return v10;
    goto LABEL_84;
  }
  (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 251);
  if ( v12 >= 0x14 )
  {
    v6 = v31;
    *v5 = 2;
    *v6 = 20;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_DDDD(v9, a2, 5, 152, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v11, *a1, 20, 20);
      v6 = v31;
    }
    goto LABEL_9;
  }
  *v5 = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_DDD(v9, a2, v13, 153, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v11, *a1, 20);
    goto LABEL_83;
  }
LABEL_84:
  v10 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_(v9, a2, 5, 166, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  }
  return v10;
}

```

## disassembly

```asm
0x1400390e4  mov     r11, rsp
0x1400390e7  mov     [r11+18h], r8
0x1400390eb  push    rbx
0x1400390ec  push    rbp
0x1400390ed  push    rsi
0x1400390ee  push    rdi
0x1400390ef  push    r12
0x1400390f1  push    r13
0x1400390f3  push    r14
0x1400390f5  push    r15
0x1400390f7  sub     rsp, 68h
0x1400390fb  mov     dword ptr [r11+10h], 0
0x140039103  mov     rsi, r9
0x140039106  mov     rax, r8
0x140039109  mov     rbx, rdx
0x14003910c  mov     rdi, rcx
0x14003910f  test    r9, r9
0x140039112  jnz     short loc_14003911A
0x140039114  lea     rsi, [r11+10h]
0x140039118  jmp     short loc_140039127
0x14003911a  cmp     byte ptr [rdx+30h], 0
0x14003911e  jz      short loc_140039127
0x140039120  mov     dword ptr [r9], 0
0x140039127  mov     r13d, [rdx+48h]
0x14003912b  lea     rcx, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140039132  mov     r15, [rsp+0A8h+arg_20]
0x14003913a  lea     r14, WPP_RECORDER_INITIALIZED
0x140039141  mov     r12d, edi
0x140039144  mov     ebp, 1
0x140039149  sub     r12d, [rdx+38h]
0x14003914d  sub     r13d, r12d
0x140039150  cmp     byte ptr [rdi], 14h
0x140039153  jnb     short loc_1400391CF
0x140039155  mov     rax, [rdx+18h]
0x140039159  mov     edx, 0FBh
0x14003915e  mov     rcx, [rbx+28h]
0x140039162  call    _guard_dispatch_icall
0x140039167  lea     ecx, [rbp+13h]
0x14003916a  cmp     r13d, ecx
0x14003916d  jb      loc_14003922E
0x140039173  mov     rax, [rsp+0A8h+arg_10]
0x14003917b  mov     dword ptr [rsi], 2
0x140039181  mov     [rax], ecx
0x140039183  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14003918a  jz      short loc_1400391C8
0x14003918c  movzx   eax, byte ptr [rdi]
0x14003918f  lea     r8d, [rbp+4]
0x140039193  mov     [rsp+0A8h+var_68], ecx
0x140039197  mov     r9d, 98h
0x14003919d  mov     [rsp+0A8h+var_70], ecx
0x1400391a1  mov     dl, 2
0x1400391a3  mov     [rsp+0A8h+var_78], eax
0x1400391a7  mov     rcx, r15
0x1400391aa  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x1400391b1  mov     [rsp+0A8h+var_80], r12d
0x1400391b6  mov     [rsp+0A8h+var_88], rax
0x1400391bb  call    WPP_RECORDER_SF_DDDD
0x1400391c0  mov     rax, [rsp+0A8h+arg_10]
0x1400391c8  lea     rcx, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x1400391cf  cmp     [rax], r13d
0x1400391d2  jbe     loc_140039275
0x1400391d8  mov     eax, 200h
0x1400391dd  cmp     [rbx], ax
0x1400391e0  ja      short loc_1400391E8
0x1400391e2  cmp     byte ptr [rbx+0Ch], 0
0x1400391e6  jz      short loc_1400391EE
0x1400391e8  mov     dword ptr [rsi], 2
0x1400391ee  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400391f5  jz      short loc_140039217
0x1400391f7  mov     [rsp+0A8h+var_80], r12d
0x1400391fc  mov     r9d, 9Ah
0x140039202  mov     [rsp+0A8h+var_88], rcx
0x140039207  mov     r8d, 5
0x14003920d  mov     rcx, r15
0x140039210  mov     dl, 2
0x140039212  call    WPP_RECORDER_SF_d
0x140039217  mov     edx, 0FDh
0x14003921c  mov     rax, [rbx+18h]
0x140039220  mov     rcx, [rbx+28h]
0x140039224  call    _guard_dispatch_icall
0x140039229  jmp     loc_140039661
0x14003922e  mov     [rsi], ebp
0x140039230  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140039237  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14003923e  jz      loc_140039666
0x140039244  movzx   eax, byte ptr [rdi]
0x140039247  mov     r9d, 99h
0x14003924d  mov     [rsp+0A8h+var_70], ecx
0x140039251  mov     dl, 2
0x140039253  mov     [rsp+0A8h+var_78], eax
0x140039257  mov     rcx, r15
0x14003925a  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140039261  mov     [rsp+0A8h+var_80], r12d
0x140039266  mov     [rsp+0A8h+var_88], rax
0x14003926b  call    WPP_RECORDER_SF_DDD
0x140039270  jmp     loc_140039661
0x140039275  cmp     byte ptr [rdi+3], 0
0x140039279  jz      short loc_1400392C5
0x14003927b  cmp     byte ptr [rbx+0Fh], 0
0x14003927f  jz      short loc_140039287
0x140039281  mov     dword ptr [rsi], 2
0x140039287  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14003928e  jz      short loc_1400392B3
0x140039290  movzx   eax, byte ptr [rdi+3]
0x140039294  mov     r9d, 9Bh
0x14003929a  mov     [rsp+0A8h+var_80], eax
0x14003929e  mov     r8d, 5
0x1400392a4  mov     [rsp+0A8h+var_88], rcx
0x1400392a9  mov     dl, 2
0x1400392ab  mov     rcx, r15
0x1400392ae  call    WPP_RECORDER_SF_d
0x1400392b3  mov     rax, [rbx+18h]
0x1400392b7  mov     edx, 0C3h
0x1400392bc  mov     rcx, [rbx+28h]
0x1400392c0  call    _guard_dispatch_icall
0x1400392c5  mov     rax, [rdi+4]
0x1400392c9  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1400392d0  jnz     short loc_140039316
0x1400392d2  mov     rax, [rdi+0Ch]
0x1400392d6  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1400392dd  jnz     short loc_140039316
0x1400392df  mov     [rsi], ebp
0x1400392e1  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400392e8  jz      short loc_14003930C
0x1400392ea  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x1400392f1  mov     r9d, 9Ch
0x1400392f7  mov     r8d, 5
0x1400392fd  mov     [rsp+0A8h+var_88], rax
0x140039302  mov     dl, 2
0x140039304  mov     rcx, r15
0x140039307  call    WPP_RECORDER_SF_
0x14003930c  mov     edx, 0C4h
0x140039311  jmp     loc_14003921C
0x140039316  mov     rax, [rdi+4]
0x14003931a  cmp     rax, qword ptr cs:GUID_USB_MSOS20_PLATFORM_CAPABILITY_ID.Data1
0x140039321  jnz     loc_14003952C
0x140039327  mov     rax, [rdi+0Ch]
0x14003932b  cmp     rax, qword ptr cs:GUID_USB_MSOS20_PLATFORM_CAPABILITY_ID.Data4
0x140039332  jnz     loc_14003952C
0x140039338  mov     rax, [rbx+50h]
0x14003933c  cmp     qword ptr [rax+30h], 0
0x140039341  jz      short loc_14003937A
0x140039343  mov     [rsi], ebp
0x140039345  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14003934c  jz      short loc_140039370
0x14003934e  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140039355  mov     r9d, 9Dh
0x14003935b  mov     r8d, 5
0x140039361  mov     [rsp+0A8h+var_88], rax
0x140039366  mov     dl, 2
0x140039368  mov     rcx, r15
0x14003936b  call    WPP_RECORDER_SF_
0x140039370  mov     edx, 0C5h
0x140039375  jmp     loc_14003921C
0x14003937a  movzx   eax, byte ptr [rdi]
0x14003937d  cmp     al, 1Ch
0x14003937f  jnb     short loc_1400393BF
0x140039381  mov     [rsi], ebp
0x140039383  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14003938a  jz      short loc_1400393B5
0x14003938c  mov     r9d, 9Eh
0x140039392  movzx   eax, byte ptr [rdi]
0x140039395  mov     r8d, 5
0x14003939b  mov     [rsp+0A8h+var_80], eax
0x14003939f  mov     dl, 2
0x1400393a1  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x1400393a8  mov     rcx, r15
0x1400393ab  mov     [rsp+0A8h+var_88], rax
0x1400393b0  call    WPP_RECORDER_SF_d
0x1400393b5  mov     edx, 0C6h
0x1400393ba  jmp     loc_14003921C
0x1400393bf  mov     r13, rax
0x1400393c2  add     eax, 0FCh
0x1400393c7  test    al, 7
0x1400393c9  jz      short loc_1400393DE
0x1400393cb  mov     [rsi], ebp
0x1400393cd  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400393d4  jz      short loc_1400393B5
0x1400393d6  mov     r9d, 9Fh
0x1400393dc  jmp     short loc_140039392
0x1400393de  add     r13, 0FFFFFFFFFFFFFFE4h
0x1400393e2  mov     [rsp+0A8h+arg_0], 0
0x1400393ed  shr     r13, 3
0x1400393f1  mov     eax, 0
0x1400393f6  add     r13d, ebp
0x1400393f9  mov     qword ptr [rsp+0A8h+var_50], r13
0x1400393fe  jz      loc_1400394F3
0x140039404  lea     r12d, [rax+1]
0x140039408  mov     edx, eax
0x14003940a  mov     [rsp+0A8h+var_58], rdx
0x14003940f  mov     [rsp+0A8h+arg_18], r12d
0x140039417  cmp     r12d, r13d
0x14003941a  jnb     short loc_140039493
0x14003941c  mov     eax, [rdi+rdx*8+14h]
0x140039420  cmp     [rdi+r12*8+14h], eax
0x140039425  jnz     short loc_14003947F
0x140039427  mov     [rsi], ebp
0x140039429  mov     rax, [rbx+50h]
0x14003942d  mov     qword ptr [rax+30h], 0
0x140039435  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14003943c  jz      short loc_140039468
0x14003943e  mov     eax, [rdi+rdx*8+14h]
0x140039442  mov     r9d, 0A0h
0x140039448  mov     [rsp+0A8h+var_80], eax
0x14003944c  mov     r8d, 5
0x140039452  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140039459  mov     dl, 2
0x14003945b  mov     rcx, r15
0x14003945e  mov     [rsp+0A8h+var_88], rax
0x140039463  call    WPP_RECORDER_SF_d
0x140039468  mov     rax, [rbx+18h]
0x14003946c  mov     edx, 0C7h
0x140039471  mov     rcx, [rbx+28h]
0x140039475  call    _guard_dispatch_icall
0x14003947a  mov     rdx, [rsp+0A8h+var_58]
0x14003947f  add     r12d, ebp
0x140039482  cmp     r12d, r13d
0x140039485  jb      short loc_14003941C
0x140039487  mov     eax, [rsp+0A8h+arg_18]
0x14003948e  jmp     loc_140039404
0x140039493  mov     r15, qword ptr [rsp+0A8h+var_50]
0x140039498  xor     r12d, r12d
0x14003949b  mov     edx, r12d
0x14003949e  lea     r13, [rdi+14h]
0x1400394a2  lea     r13, [r13+r12*8+0]
0x1400394a7  mov     ecx, [r13+0]; Version
0x1400394ab  cmp     ecx, edx
0x1400394ad  jbe     short loc_1400394DB
0x1400394af  call    cs:__imp_RtlIsNtDdiVersionAvailable
0x1400394b6  nop     dword ptr [rax+rax+00h]
0x1400394bb  test    al, al
0x1400394bd  jz      short loc_1400394D4
0x1400394bf  mov     edx, [r13+0]
0x1400394c3  mov     rax, [rbx+50h]
0x1400394c7  mov     [rsp+0A8h+arg_0], edx
0x1400394ce  mov     [rax+30h], r13
0x1400394d2  jmp     short loc_1400394DB
0x1400394d4  mov     edx, [rsp+0A8h+arg_0]
0x1400394db  add     r12d, ebp
0x1400394de  cmp     r12d, r15d
0x1400394e1  jb      short loc_14003949E
0x1400394e3  mov     r15, [rsp+0A8h+arg_20]
0x1400394eb  test    edx, edx
0x1400394ed  jnz     loc_140039661
0x1400394f3  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400394fa  jz      short loc_14003951E
0x1400394fc  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140039503  mov     r9d, 0A1h
0x140039509  mov     r8d, 5
0x14003950f  mov     [rsp+0A8h+var_88], rax
0x140039514  mov     dl, 2
0x140039516  mov     rcx, r15
0x140039519  call    WPP_RECORDER_SF_
0x14003951e  mov     rax, [rbx+20h]
0x140039522  mov     edx, 0C8h
0x140039527  jmp     loc_140039220
0x14003952c  mov     rax, [rdi+4]
0x140039530  cmp     rax, qword ptr cs:GUID_USB_PLATFORM_FEATURES.Data1
0x140039537  jnz     loc_140039661
0x14003953d  mov     rax, [rdi+0Ch]
0x140039541  cmp     rax, qword ptr cs:GUID_USB_PLATFORM_FEATURES.Data4
0x140039548  jnz     loc_140039661
0x14003954e  mov     al, [rdi]
0x140039550  cmp     al, 1Ah
0x140039552  jnb     short loc_140039592
0x140039554  mov     [rsi], ebp
0x140039556  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14003955d  jz      short loc_140039588
0x14003955f  movzx   eax, byte ptr [rdi]
0x140039562  mov     r9d, 0A2h
0x140039568  mov     [rsp+0A8h+var_80], eax
0x14003956c  mov     r8d, 5
0x140039572  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140039579  mov     dl, 2
0x14003957b  mov     rcx, r15
0x14003957e  mov     [rsp+0A8h+var_88], rax
0x140039583  call    WPP_RECORDER_SF_d
0x140039588  mov     edx, 0FAh
0x14003958d  jmp     loc_14003921C
0x140039592  cmp     [rdi+14h], bpl
0x140039596  jnz     short loc_1400395DA
0x140039598  cmp     al, 1Ah
0x14003959a  jz      short loc_14003961B
0x14003959c  mov     [rsi], ebp
0x14003959e  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400395a5  jz      short loc_1400395D0
0x1400395a7  movzx   eax, byte ptr [rdi]
0x1400395aa  mov     r9d, 0A3h
0x1400395b0  mov     [rsp+0A8h+var_80], eax
0x1400395b4  mov     r8d, 5
0x1400395ba  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x1400395c1  mov     dl, 2
0x1400395c3  mov     rcx, r15
0x1400395c6  mov     [rsp+0A8h+var_88], rax
0x1400395cb  call    WPP_RECORDER_SF_d
0x1400395d0  mov     edx, 0F7h
0x1400395d5  jmp     loc_14003921C
0x1400395da  jnb     short loc_14003961B
0x1400395dc  mov     [rsi], ebp
0x1400395de  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
  ... truncated ...
```
