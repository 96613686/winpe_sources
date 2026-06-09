# RaidAdapterQueryInterfaceIrp

- ea: `0x14008ae24`
- end: `0x14008b2de`
- name: `RaidAdapterQueryInterfaceIrp`
- size: `1210`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400234a0`

## callees

- `0x140025144`
- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x14008ae24`
- `0x1400a435c`
- `0x1400bb694`
- `0x14014b400`
- `0x1401b80f8`
- `0x1401b8138`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14008af48`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14008b005`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14008af48`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14008b005`
- `ntoskrnl!IofCompleteRequest` at `0x14008b2a7`
- `ntoskrnl!IofCompleteRequest` at `0x14008b2a7`
- `ntoskrnl!RtlCompareMemory` at `0x14008ae73`
- `ntoskrnl!RtlCompareMemory` at `0x14008ae9f`
- `ntoskrnl!RtlCompareMemory` at `0x14008aecb`
- `ntoskrnl!RtlCompareMemory` at `0x14008aef3`
- `ntoskrnl!RtlCompareMemory` at `0x14008ae73`
- `ntoskrnl!RtlCompareMemory` at `0x14008ae9f`
- `ntoskrnl!RtlCompareMemory` at `0x14008aecb`
- `ntoskrnl!RtlCompareMemory` at `0x14008aef3`

## pseudocode

```c
__int64 __fastcall RaidAdapterQueryInterfaceIrp(_QWORD *a1, __int64 a2)
{
  __int64 v2; // rdi
  GUID *v5; // rcx
  GUID *v6; // rcx
  GUID *v7; // rcx
  __int64 *v8; // rcx
  int NotificationInterface; // edi
  bool v10; // zf
  unsigned __int64 v11; // rcx
  __int64 v12; // rdx
  int *v13; // rax
  int v14; // ecx
  int CoolingInterface; // eax
  int InterfaceFdoInfo; // eax
  __int64 v17; // rcx
  __int64 *v18; // rdx
  __int64 v19; // rdx
  char v20; // r10
  unsigned int v21; // r15d
  unsigned __int8 v22; // r11
  char *v23; // rsi
  char v24; // r12
  _BYTE *v25; // r9
  __int64 v26; // r14
  char v27; // r13
  unsigned __int64 v28; // rbp
  __int64 v29; // r8
  int v30; // ecx
  char v31; // cl
  char v32; // bp
  char v33; // si
  char v34; // r8
  _BYTE *v35; // rax
  char *v36; // r8
  unsigned int v37; // eax
  __int128 v39; // [rsp+60h] [rbp-58h] BYREF

  v2 = *(_QWORD *)(a2 + 184);
  v5 = *(GUID **)(v2 + 8);
  if ( v5 == &GUID_STORAGE_QUERY_FDO_INFO || RtlCompareMemory(v5, &GUID_STORAGE_QUERY_FDO_INFO, 0x10u) == 16 )
  {
    InterfaceFdoInfo = PortQueryInterfaceFdoInfo(v5, a2, a1[4]);
    goto LABEL_22;
  }
  v6 = *(GUID **)(v2 + 8);
  if ( v6 == &GUID_STORAGE_QUERY_FDO_DEVICE_RELATIONS
    || RtlCompareMemory(v6, &GUID_STORAGE_QUERY_FDO_DEVICE_RELATIONS, 0x10u) == 16 )
  {
    InterfaceFdoInfo = PortQueryInterfaceFdoQdr(v6, a2, a1[555]);
LABEL_22:
    NotificationInterface = InterfaceFdoInfo;
    *(_DWORD *)(a2 + 48) = InterfaceFdoInfo;
    CoolingInterface = ~InterfaceFdoInfo;
    goto LABEL_23;
  }
  v7 = *(GUID **)(v2 + 8);
  if ( v7 != &GUID_THERMAL_COOLING_INTERFACE && RtlCompareMemory(v7, &GUID_THERMAL_COOLING_INTERFACE, 0x10u) != 16 )
  {
    v8 = *(__int64 **)(v2 + 8);
    if ( v8 == qword_140157880 || RtlCompareMemory(v8, qword_140157880, 0x10u) == 16 )
    {
      NotificationInterface = StorNvmeQueryNotificationInterface(a1 + 788, a2);
      if ( NotificationInterface >= 0 )
        goto LABEL_10;
    }
LABEL_24:
    if ( StorEtwLoggingEnabled )
    {
      v39 = 0;
      IoGetActivityIdIrp(a2, &v39);
      if ( (byte_140177432 & 0x20) != 0 )
        McTemplateK0pd_EtwWriteTransfer(v17, EventPnpRequestComplete, &v39, a2, *(_DWORD *)(a2 + 48));
    }
    return (unsigned int)RaForwardIrp(a1[3], a2);
  }
  CoolingInterface = RaidAdapterQueryCoolingInterface(a1, a2);
  NotificationInterface = CoolingInterface;
LABEL_23:
  if ( CoolingInterface < 0 )
    goto LABEL_24;
LABEL_10:
  v10 = StorEtwLoggingEnabled == 0;
  *(_BYTE *)(a2 + 141) = -84;
  *(_DWORD *)(a2 + 48) = NotificationInterface;
  if ( v10 )
    goto LABEL_83;
  v39 = 0;
  IoGetActivityIdIrp(a2, &v39);
  v12 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)v12 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_83;
    v18 = EventNonReadWriteRequestComplete;
    goto LABEL_82;
  }
  if ( *(_BYTE *)v12 != 15 )
  {
    if ( *(_BYTE *)v12 != 27 )
      goto LABEL_83;
    if ( *(_BYTE *)(v12 + 1) == 7 && !*(_DWORD *)(v12 + 8) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v13 = *(int **)(a2 + 56);
        if ( v13 )
          v14 = *v13;
        else
          v14 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v14, v12, (unsigned int)&v39, a2, v14, *(_DWORD *)(a2 + 48));
      }
      goto LABEL_83;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_83;
    v18 = EventPnpRequestComplete;
LABEL_82:
    McTemplateK0pd_EtwWriteTransfer(v11, v18, &v39, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_83;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_83;
  v19 = *(_QWORD *)(v12 + 8);
  v20 = 1;
  if ( *(_BYTE *)(v19 + 2) == 40 )
  {
    if ( *(_DWORD *)(v19 + 20) )
      goto LABEL_83;
    v21 = *(_DWORD *)(v19 + 56);
    if ( !v21 )
      goto LABEL_83;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    while ( 1 )
    {
      v11 = *(unsigned int *)(v19 + 4 * v26 + 120);
      if ( (unsigned int)v11 >= 0x80 )
      {
        v28 = *(unsigned int *)(v19 + 16);
        if ( (unsigned int)v11 < (unsigned int)v28 )
        {
          v29 = (unsigned int)v11;
          v30 = *(_DWORD *)(v11 + v19) - 64;
          if ( v30 )
          {
            LODWORD(v11) = v30 - 1;
            if ( (_DWORD)v11 )
            {
              if ( (_DWORD)v11 == 1 )
              {
                LODWORD(v11) = v29 + 40;
                if ( v29 + 40 <= v28 )
                {
                  if ( *(_DWORD *)(v29 + v19 + 12) )
                    v23 = (char *)(v29 + v19 + 32);
                  v25 = *(_BYTE **)(v29 + v19 + 24);
                  goto LABEL_57;
                }
              }
            }
            else
            {
              LODWORD(v11) = v29 + 56;
              if ( v29 + 56 <= v28 )
              {
                v27 = 1;
                if ( *(_BYTE *)(v29 + v19 + 10) )
                  v23 = (char *)(v29 + v19 + 24);
                v24 = *(_BYTE *)(v29 + v19 + 8);
                v25 = *(_BYTE **)(v29 + v19 + 16);
                v22 = *(_BYTE *)(v29 + v19 + 9);
              }
            }
          }
          else
          {
            LODWORD(v11) = v29 + 40;
            if ( v29 + 40 <= v28 )
            {
              if ( *(_BYTE *)(v29 + v19 + 10) )
                v23 = (char *)(v29 + v19 + 24);
              v25 = *(_BYTE **)(v29 + v19 + 16);
LABEL_57:
              v22 = *(_BYTE *)(v29 + v19 + 9);
              v24 = *(_BYTE *)(v29 + v19 + 8);
LABEL_58:
              if ( v23 )
              {
                v31 = *v23;
                goto LABEL_61;
              }
              goto LABEL_83;
            }
          }
          if ( v27 )
            goto LABEL_58;
        }
      }
      v26 = (unsigned int)(v26 + 1);
      if ( (unsigned int)v26 >= v21 )
        goto LABEL_58;
    }
  }
  v31 = *(_BYTE *)(v19 + 72);
  v25 = *(_BYTE **)(v19 + 32);
  v22 = *(_BYTE *)(v19 + 11);
  v24 = *(_BYTE *)(v19 + 4);
  if ( *(_BYTE *)(v19 + 2) )
    goto LABEL_83;
LABEL_61:
  LOBYTE(v11) = v31 - 8;
  if ( (v11 & 0x5D) == 0 )
  {
    v32 = *(_BYTE *)(v19 + 3);
    if ( v32 == 1 || !v25 || !v22 )
      goto LABEL_78;
    LOBYTE(v19) = 0;
    v33 = 0;
    v34 = 0;
    v11 = (unsigned __int64)&v25[v22];
    v35 = v25 + 8;
    if ( (unsigned __int8)((*v25 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v35 <= v11 )
      {
        v33 = v25[2];
        LOBYTE(v19) = v25[1] & 0xF;
        v34 = v25[3];
        goto LABEL_77;
      }
    }
    else if ( (unsigned __int64)v35 <= v11 )
    {
      v36 = v25 + 13;
      LOBYTE(v19) = v25[2] & 0xF;
      v37 = v22;
      if ( (unsigned int)(unsigned __int8)v25[7] + 8 <= v22 )
        v37 = (unsigned __int8)v25[7] + 8;
      v11 = (unsigned __int64)&v25[v37];
      if ( (unsigned __int64)v36 <= v11 )
        v33 = v25[12];
      if ( (unsigned __int64)(v25 + 14) > v11 )
        v34 = 0;
      else
        v34 = *v36;
LABEL_77:
      if ( v20 )
      {
LABEL_79:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v11,
          v19,
          (unsigned int)&v39,
          a2,
          *(_DWORD *)(a2 + 48),
          v32,
          v24,
          v19,
          v33,
          v34,
          a2);
        goto LABEL_83;
      }
LABEL_78:
      LOBYTE(v19) = 0;
      v33 = 0;
      v34 = 0;
      goto LABEL_79;
    }
    v20 = 0;
    goto LABEL_77;
  }
LABEL_83:
  IofCompleteRequest((PIRP)a2, 0);
  return (unsigned int)NotificationInterface;
}

```

## disassembly

```asm
0x14008ae24  mov     [rsp+arg_10], rbx
0x14008ae29  push    rbp
0x14008ae2a  push    rsi
0x14008ae2b  push    rdi
0x14008ae2c  push    r12
0x14008ae2e  push    r13
0x14008ae30  push    r14
0x14008ae32  push    r15
0x14008ae34  sub     rsp, 80h
0x14008ae3b  mov     rax, cs:__security_cookie
0x14008ae42  xor     rax, rsp
0x14008ae45  mov     [rsp+0B8h+var_48], rax
0x14008ae4a  mov     rdi, [rdx+0B8h]
0x14008ae51  mov     rbx, rdx
0x14008ae54  mov     rsi, rcx
0x14008ae57  lea     rdx, GUID_STORAGE_QUERY_FDO_INFO; Source2
0x14008ae5e  mov     rcx, [rdi+8]; Source1
0x14008ae62  cmp     rcx, rdx
0x14008ae65  jz      loc_14008AFCE
0x14008ae6b  mov     ebp, 10h
0x14008ae70  mov     r8d, ebp; Length
0x14008ae73  call    cs:__imp_RtlCompareMemory
0x14008ae7a  nop     dword ptr [rax+rax+00h]
0x14008ae7f  cmp     rax, rbp
0x14008ae82  jz      loc_14008AFCE
0x14008ae88  mov     rcx, [rdi+8]; Source1
0x14008ae8c  lea     rdx, GUID_STORAGE_QUERY_FDO_DEVICE_RELATIONS; Source2
0x14008ae93  cmp     rcx, rdx
0x14008ae96  jz      loc_14008AFBD
0x14008ae9c  mov     r8d, ebp; Length
0x14008ae9f  call    cs:__imp_RtlCompareMemory
0x14008aea6  nop     dword ptr [rax+rax+00h]
0x14008aeab  cmp     rax, rbp
0x14008aeae  jz      loc_14008AFBD
0x14008aeb4  mov     rcx, [rdi+8]; Source1
0x14008aeb8  lea     rdx, GUID_THERMAL_COOLING_INTERFACE; Source2
0x14008aebf  cmp     rcx, rdx
0x14008aec2  jz      loc_14008AFAE
0x14008aec8  mov     r8d, ebp; Length
0x14008aecb  call    cs:__imp_RtlCompareMemory
0x14008aed2  nop     dword ptr [rax+rax+00h]
0x14008aed7  cmp     rax, rbp
0x14008aeda  jz      loc_14008AFAE
0x14008aee0  mov     rcx, [rdi+8]; Source1
0x14008aee4  lea     rdx, qword_140157880; Source2
0x14008aeeb  cmp     rcx, rdx
0x14008aeee  jz      short loc_14008AF08
0x14008aef0  mov     r8d, ebp; Length
0x14008aef3  call    cs:__imp_RtlCompareMemory
0x14008aefa  nop     dword ptr [rax+rax+00h]
0x14008aeff  cmp     rax, rbp
0x14008af02  jnz     loc_14008AFEC
0x14008af08  lea     rcx, [rsi+18A0h]
0x14008af0f  mov     rdx, rbx
0x14008af12  call    StorNvmeQueryNotificationInterface
0x14008af17  mov     edi, eax
0x14008af19  test    eax, eax
0x14008af1b  js      loc_14008AFEC
0x14008af21  cmp     cs:StorEtwLoggingEnabled, 0
0x14008af28  mov     byte ptr [rbx+8Dh], 0ACh
0x14008af2f  mov     [rbx+30h], edi
0x14008af32  jz      loc_14008B2A2
0x14008af38  xorps   xmm0, xmm0
0x14008af3b  lea     rdx, [rsp+0B8h+var_58]
0x14008af40  mov     rcx, rbx
0x14008af43  movups  [rsp+0B8h+var_58], xmm0
0x14008af48  call    cs:__imp_IoGetActivityIdIrp
0x14008af4f  nop     dword ptr [rax+rax+00h]
0x14008af54  mov     rdx, [rbx+0B8h]
0x14008af5b  movzx   eax, byte ptr [rdx]
0x14008af5e  sub     eax, 0Eh
0x14008af61  jz      loc_14008B27E
0x14008af67  sub     eax, 1
0x14008af6a  jz      loc_14008B080
0x14008af70  cmp     eax, 0Ch
0x14008af73  jnz     loc_14008B2A2
0x14008af79  cmp     byte ptr [rdx+1], 7
0x14008af7d  jnz     loc_14008B067
0x14008af83  cmp     dword ptr [rdx+8], 0
0x14008af87  jnz     loc_14008B067
0x14008af8d  test    cs:byte_140177432, 40h
0x14008af94  jz      loc_14008B2A2
0x14008af9a  mov     rax, [rbx+38h]
0x14008af9e  test    rax, rax
0x14008afa1  jz      loc_14008B048
0x14008afa7  mov     ecx, [rax]
0x14008afa9  jmp     loc_14008B04A
0x14008afae  mov     rdx, rbx
0x14008afb1  mov     rcx, rsi
0x14008afb4  call    RaidAdapterQueryCoolingInterface
0x14008afb9  mov     edi, eax
0x14008afbb  jmp     short loc_14008AFE1
0x14008afbd  mov     r8, [rsi+1158h]
0x14008afc4  mov     rdx, rbx
0x14008afc7  call    PortQueryInterfaceFdoQdr
0x14008afcc  jmp     short loc_14008AFDA
0x14008afce  mov     r8, [rsi+20h]
0x14008afd2  mov     rdx, rbx
0x14008afd5  call    PortQueryInterfaceFdoInfo
0x14008afda  mov     edi, eax
0x14008afdc  mov     [rbx+30h], eax
0x14008afdf  not     eax
0x14008afe1  shr     eax, 1Fh
0x14008afe4  test    al, al
0x14008afe6  jz      loc_14008AF21
0x14008afec  cmp     cs:StorEtwLoggingEnabled, 0
0x14008aff3  jz      short loc_14008B035
0x14008aff5  xorps   xmm0, xmm0
0x14008aff8  lea     rdx, [rsp+0B8h+var_58]
0x14008affd  mov     rcx, rbx
0x14008b000  movups  [rsp+0B8h+var_58], xmm0
0x14008b005  call    cs:__imp_IoGetActivityIdIrp
0x14008b00c  nop     dword ptr [rax+rax+00h]
0x14008b011  test    cs:byte_140177432, 20h
0x14008b018  jz      short loc_14008B035
0x14008b01a  mov     eax, [rbx+30h]
0x14008b01d  lea     r8, [rsp+0B8h+var_58]
0x14008b022  mov     r9, rbx
0x14008b025  mov     [rsp+0B8h+var_98], eax
0x14008b029  lea     rdx, EventPnpRequestComplete
0x14008b030  call    McTemplateK0pd_EtwWriteTransfer
0x14008b035  mov     rcx, [rsi+18h]
0x14008b039  mov     rdx, rbx
0x14008b03c  call    RaForwardIrp
0x14008b041  mov     edi, eax
0x14008b043  jmp     loc_14008B2B3
0x14008b048  xor     ecx, ecx
0x14008b04a  mov     eax, [rbx+30h]
0x14008b04d  lea     r8, [rsp+0B8h+var_58]
0x14008b052  mov     [rsp+0B8h+var_90], eax
0x14008b056  mov     r9, rbx
0x14008b059  mov     [rsp+0B8h+var_98], ecx
0x14008b05d  call    McTemplateK0pqd_EtwWriteTransfer
0x14008b062  jmp     loc_14008B2A2
0x14008b067  test    cs:byte_140177432, 20h
0x14008b06e  jz      loc_14008B2A2
0x14008b074  lea     rdx, EventPnpRequestComplete
0x14008b07b  jmp     loc_14008B28E
0x14008b080  cmp     cs:byte_140177431, 0
0x14008b087  jge     loc_14008B2A2
0x14008b08d  mov     rdx, [rdx+8]
0x14008b091  mov     r10d, 1
0x14008b097  movzx   eax, byte ptr [rdx+2]
0x14008b09b  cmp     al, 28h ; '('
0x14008b09d  jnz     loc_14008B186
0x14008b0a3  cmp     dword ptr [rdx+14h], 0
0x14008b0a7  jnz     loc_14008B2A2
0x14008b0ad  mov     r15d, [rdx+38h]
0x14008b0b1  test    r15d, r15d
0x14008b0b4  jz      loc_14008B2A2
0x14008b0ba  xor     r11b, r11b
0x14008b0bd  xor     esi, esi
0x14008b0bf  xor     r12b, r12b
0x14008b0c2  xor     r9d, r9d
0x14008b0c5  xor     r14d, r14d
0x14008b0c8  xor     r13b, r13b
0x14008b0cb  mov     ecx, [rdx+r14*4+78h]
0x14008b0d0  cmp     ecx, 80h
0x14008b0d6  jb      short loc_14008B14D
0x14008b0d8  mov     ebp, [rdx+10h]
0x14008b0db  cmp     ecx, ebp
0x14008b0dd  jnb     short loc_14008B14D
0x14008b0df  mov     r8d, ecx
0x14008b0e2  mov     ecx, [rcx+rdx]
0x14008b0e5  sub     ecx, 40h ; '@'
0x14008b0e8  jz      short loc_14008B13F
0x14008b0ea  sub     ecx, r10d
0x14008b0ed  jz      short loc_14008B113
0x14008b0ef  cmp     ecx, r10d
0x14008b0f2  jnz     short loc_14008B148
0x14008b0f4  lea     rcx, [r8+28h]
0x14008b0f8  cmp     rcx, rbp
0x14008b0fb  ja      short loc_14008B148
0x14008b0fd  cmp     dword ptr [r8+rdx+0Ch], 0
0x14008b103  jbe     short loc_14008B10C
0x14008b105  lea     rsi, [rdx+20h]
0x14008b109  add     rsi, r8
0x14008b10c  mov     r9, [r8+rdx+18h]
0x14008b111  jmp     short loc_14008B16F
0x14008b113  lea     rcx, [r8+38h]
0x14008b117  cmp     rcx, rbp
0x14008b11a  ja      short loc_14008B148
0x14008b11c  cmp     byte ptr [r8+rdx+0Ah], 0
0x14008b122  mov     r13b, r10b
0x14008b125  jbe     short loc_14008B12E
0x14008b127  lea     rsi, [rdx+18h]
0x14008b12b  add     rsi, r8
0x14008b12e  mov     r12b, [r8+rdx+8]
0x14008b133  mov     r9, [r8+rdx+10h]
0x14008b138  mov     r11b, [r8+rdx+9]
0x14008b13d  jmp     short loc_14008B148
0x14008b13f  lea     rcx, [r8+28h]
0x14008b143  cmp     rcx, rbp
0x14008b146  jbe     short loc_14008B15B
0x14008b148  test    r13b, r13b
0x14008b14b  jnz     short loc_14008B179
0x14008b14d  add     r14d, r10d
0x14008b150  cmp     r14d, r15d
0x14008b153  jb      loc_14008B0CB
0x14008b159  jmp     short loc_14008B179
0x14008b15b  cmp     byte ptr [r8+rdx+0Ah], 0
0x14008b161  jbe     short loc_14008B16A
0x14008b163  lea     rsi, [rdx+18h]
0x14008b167  add     rsi, r8
0x14008b16a  mov     r9, [r8+rdx+10h]
0x14008b16f  mov     r11b, [r8+rdx+9]
0x14008b174  mov     r12b, [r8+rdx+8]
0x14008b179  test    rsi, rsi
0x14008b17c  jz      loc_14008B2A2
0x14008b182  mov     cl, [rsi]
0x14008b184  jmp     short loc_14008B19D
0x14008b186  mov     cl, [rdx+48h]
0x14008b189  mov     r9, [rdx+20h]
0x14008b18d  mov     r11b, [rdx+0Bh]
0x14008b191  mov     r12b, [rdx+4]
0x14008b195  test    eax, eax
0x14008b197  jnz     loc_14008B2A2
0x14008b19d  sub     cl, 8
0x14008b1a0  test    cl, 5Dh
0x14008b1a3  jnz     loc_14008B2A2
0x14008b1a9  mov     bpl, [rdx+3]
0x14008b1ad  cmp     bpl, r10b
0x14008b1b0  jz      loc_14008B243
0x14008b1b6  test    r9, r9
0x14008b1b9  jz      loc_14008B243
0x14008b1bf  test    r11b, r11b
0x14008b1c2  jz      short loc_14008B243
0x14008b1c4  mov     al, [r9]
0x14008b1c7  xor     dl, dl
0x14008b1c9  and     al, 7Fh
0x14008b1cb  movzx   ecx, r11b
0x14008b1cf  sub     al, 72h ; 'r'
0x14008b1d1  xor     sil, sil
0x14008b1d4  xor     r8b, r8b
0x14008b1d7  add     rcx, r9
0x14008b1da  cmp     al, r10b
0x14008b1dd  lea     rax, [r9+8]
0x14008b1e1  jbe     short loc_14008B225
0x14008b1e3  cmp     rax, rcx
0x14008b1e6  ja      short loc_14008B23B
0x14008b1e8  movzx   ecx, byte ptr [r9+7]
0x14008b1ed  lea     r8, [r9+0Dh]
0x14008b1f1  mov     dl, [r9+2]
0x14008b1f5  add     ecx, 8
0x14008b1f8  and     dl, 0Fh
0x14008b1fb  movzx   eax, r11b
0x14008b1ff  cmp     ecx, eax
0x14008b201  cmovbe  eax, ecx
0x14008b204  mov     ecx, eax
0x14008b206  add     rcx, r9
0x14008b209  cmp     r8, rcx
0x14008b20c  ja      short loc_14008B212
0x14008b20e  mov     sil, [r9+0Ch]
0x14008b212  lea     rax, [r9+0Eh]
0x14008b216  cmp     rax, rcx
0x14008b219  ja      short loc_14008B220
0x14008b21b  mov     r8b, [r8]
0x14008b21e  jmp     short loc_14008B23E
0x14008b220  xor     r8b, r8b
0x14008b223  jmp     short loc_14008B23E
0x14008b225  cmp     rax, rcx
0x14008b228  ja      short loc_14008B23B
0x14008b22a  mov     dl, [r9+1]
0x14008b22e  mov     sil, [r9+2]
0x14008b232  and     dl, 0Fh
0x14008b235  mov     r8b, [r9+3]
0x14008b239  jmp     short loc_14008B23E
0x14008b23b  xor     r10b, r10b
0x14008b23e  test    r10b, r10b
0x14008b241  jnz     short loc_14008B24B
0x14008b243  xor     dl, dl
0x14008b245  xor     sil, sil
0x14008b248  xor     r8b, r8b
0x14008b24b  mov     eax, [rbx+30h]
0x14008b24e  mov     r9, rbx
0x14008b251  mov     [rsp+0B8h+var_68], rbx
0x14008b256  mov     [rsp+0B8h+var_70], r8b
0x14008b25b  lea     r8, [rsp+0B8h+var_58]
0x14008b260  mov     [rsp+0B8h+var_78], sil
0x14008b265  mov     [rsp+0B8h+var_80], dl
0x14008b269  mov     [rsp+0B8h+var_88], r12b
0x14008b26e  mov     byte ptr [rsp+0B8h+var_90], bpl
0x14008b273  mov     [rsp+0B8h+var_98], eax
0x14008b277  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x14008b27c  jmp     short loc_14008B2A2
0x14008b27e  test    cs:byte_140177432, 8
0x14008b285  jz      short loc_14008B2A2
0x14008b287  lea     rdx, EventNonReadWriteRequestComplete
0x14008b28e  mov     eax, [rbx+30h]
0x14008b291  lea     r8, [rsp+0B8h+var_58]
0x14008b296  mov     r9, rbx
0x14008b299  mov     [rsp+0B8h+var_98], eax
0x14008b29d  call    McTemplateK0pd_EtwWriteTransfer
0x14008b2a2  xor     edx, edx; PriorityBoost
0x14008b2a4  mov     rcx, rbx; Irp
0x14008b2a7  call    cs:__imp_IofCompleteRequest
0x14008b2ae  nop     dword ptr [rax+rax+00h]
0x14008b2b3  mov     eax, edi
0x14008b2b5  mov     rcx, [rsp+0B8h+var_48]
0x14008b2ba  xor     rcx, rsp; StackCookie
  ... truncated ...
```
