# NvmeAdapterQueryInterfaceIrp

- ea: `0x1400fc3d8`
- end: `0x1400fc898`
- name: `NvmeAdapterQueryInterfaceIrp`
- size: `1216`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400fb0d8`

## callees

- `0x140025144`
- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x1400bb694`
- `0x1400fc3d8`
- `0x14013aa20`
- `0x14014b400`
- `0x1401b80f8`
- `0x1401b8138`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x1400fc507`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400fc5bc`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400fc507`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400fc5bc`
- `ntoskrnl!IofCompleteRequest` at `0x1400fc85e`
- `ntoskrnl!IofCompleteRequest` at `0x1400fc85e`
- `ntoskrnl!RtlCompareMemory` at `0x1400fc432`
- `ntoskrnl!RtlCompareMemory` at `0x1400fc45e`
- `ntoskrnl!RtlCompareMemory` at `0x1400fc48a`
- `ntoskrnl!RtlCompareMemory` at `0x1400fc4b2`
- `ntoskrnl!RtlCompareMemory` at `0x1400fc432`
- `ntoskrnl!RtlCompareMemory` at `0x1400fc45e`
- `ntoskrnl!RtlCompareMemory` at `0x1400fc48a`
- `ntoskrnl!RtlCompareMemory` at `0x1400fc4b2`

## pseudocode

```c
__int64 __fastcall NvmeAdapterQueryInterfaceIrp(_QWORD *a1, __int64 a2)
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
  __int128 v39; // [rsp+60h] [rbp-68h] BYREF
  __int128 v40; // [rsp+70h] [rbp-58h] BYREF

  v2 = *(_QWORD *)(a2 + 184);
  v40 = 0;
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
    InterfaceFdoInfo = PortQueryInterfaceFdoQdr(v6, a2, a1[127]);
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
    if ( v8 == qword_14015DCE0 || RtlCompareMemory(v8, qword_14015DCE0, 0x10u) == 16 )
    {
      NotificationInterface = StorNvmeQueryNotificationInterface(a1 + 170, a2);
      if ( NotificationInterface >= 0 )
        goto LABEL_10;
    }
LABEL_24:
    if ( StorEtwLoggingEnabled )
    {
      IoGetActivityIdIrp(a2, &v40);
      if ( (byte_140177432 & 0x20) != 0 )
        McTemplateK0pd_EtwWriteTransfer(v17, EventPnpRequestComplete, &v40, a2, *(_DWORD *)(a2 + 48));
    }
    return (unsigned int)RaForwardIrp(a1[3], a2);
  }
  CoolingInterface = NvmeAdapterQueryCoolingInterface(a1, a2);
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
0x1400fc3d8  mov     [rsp+arg_10], rbx
0x1400fc3dd  push    rbp
0x1400fc3de  push    rsi
0x1400fc3df  push    rdi
0x1400fc3e0  push    r12
0x1400fc3e2  push    r13
0x1400fc3e4  push    r14
0x1400fc3e6  push    r15
0x1400fc3e8  sub     rsp, 90h
0x1400fc3ef  mov     rax, cs:__security_cookie
0x1400fc3f6  xor     rax, rsp
0x1400fc3f9  mov     [rsp+0C8h+var_48], rax
0x1400fc401  mov     rdi, [rdx+0B8h]
0x1400fc408  xorps   xmm0, xmm0
0x1400fc40b  mov     rbx, rdx
0x1400fc40e  mov     rsi, rcx
0x1400fc411  movups  [rsp+0C8h+var_58], xmm0
0x1400fc416  lea     rdx, GUID_STORAGE_QUERY_FDO_INFO; Source2
0x1400fc41d  mov     rcx, [rdi+8]; Source1
0x1400fc421  cmp     rcx, rdx
0x1400fc424  jz      loc_1400FC58D
0x1400fc42a  mov     ebp, 10h
0x1400fc42f  mov     r8d, ebp; Length
0x1400fc432  call    cs:__imp_RtlCompareMemory
0x1400fc439  nop     dword ptr [rax+rax+00h]
0x1400fc43e  cmp     rax, rbp
0x1400fc441  jz      loc_1400FC58D
0x1400fc447  mov     rcx, [rdi+8]; Source1
0x1400fc44b  lea     rdx, GUID_STORAGE_QUERY_FDO_DEVICE_RELATIONS; Source2
0x1400fc452  cmp     rcx, rdx
0x1400fc455  jz      loc_1400FC57C
0x1400fc45b  mov     r8d, ebp; Length
0x1400fc45e  call    cs:__imp_RtlCompareMemory
0x1400fc465  nop     dword ptr [rax+rax+00h]
0x1400fc46a  cmp     rax, rbp
0x1400fc46d  jz      loc_1400FC57C
0x1400fc473  mov     rcx, [rdi+8]; Source1
0x1400fc477  lea     rdx, GUID_THERMAL_COOLING_INTERFACE; Source2
0x1400fc47e  cmp     rcx, rdx
0x1400fc481  jz      loc_1400FC56D
0x1400fc487  mov     r8d, ebp; Length
0x1400fc48a  call    cs:__imp_RtlCompareMemory
0x1400fc491  nop     dword ptr [rax+rax+00h]
0x1400fc496  cmp     rax, rbp
0x1400fc499  jz      loc_1400FC56D
0x1400fc49f  mov     rcx, [rdi+8]; Source1
0x1400fc4a3  lea     rdx, qword_14015DCE0; Source2
0x1400fc4aa  cmp     rcx, rdx
0x1400fc4ad  jz      short loc_1400FC4C7
0x1400fc4af  mov     r8d, ebp; Length
0x1400fc4b2  call    cs:__imp_RtlCompareMemory
0x1400fc4b9  nop     dword ptr [rax+rax+00h]
0x1400fc4be  cmp     rax, rbp
0x1400fc4c1  jnz     loc_1400FC5AB
0x1400fc4c7  lea     rcx, [rsi+550h]
0x1400fc4ce  mov     rdx, rbx
0x1400fc4d1  call    StorNvmeQueryNotificationInterface
0x1400fc4d6  mov     edi, eax
0x1400fc4d8  test    eax, eax
0x1400fc4da  js      loc_1400FC5AB
0x1400fc4e0  cmp     cs:StorEtwLoggingEnabled, 0
0x1400fc4e7  mov     byte ptr [rbx+8Dh], 0ACh
0x1400fc4ee  mov     [rbx+30h], edi
0x1400fc4f1  jz      loc_1400FC859
0x1400fc4f7  xorps   xmm0, xmm0
0x1400fc4fa  lea     rdx, [rsp+0C8h+var_68]
0x1400fc4ff  mov     rcx, rbx
0x1400fc502  movups  [rsp+0C8h+var_68], xmm0
0x1400fc507  call    cs:__imp_IoGetActivityIdIrp
0x1400fc50e  nop     dword ptr [rax+rax+00h]
0x1400fc513  mov     rdx, [rbx+0B8h]
0x1400fc51a  movzx   eax, byte ptr [rdx]
0x1400fc51d  sub     eax, 0Eh
0x1400fc520  jz      loc_1400FC835
0x1400fc526  sub     eax, 1
0x1400fc529  jz      loc_1400FC637
0x1400fc52f  cmp     eax, 0Ch
0x1400fc532  jnz     loc_1400FC859
0x1400fc538  cmp     byte ptr [rdx+1], 7
0x1400fc53c  jnz     loc_1400FC61E
0x1400fc542  cmp     dword ptr [rdx+8], 0
0x1400fc546  jnz     loc_1400FC61E
0x1400fc54c  test    cs:byte_140177432, 40h
0x1400fc553  jz      loc_1400FC859
0x1400fc559  mov     rax, [rbx+38h]
0x1400fc55d  test    rax, rax
0x1400fc560  jz      loc_1400FC5FF
0x1400fc566  mov     ecx, [rax]
0x1400fc568  jmp     loc_1400FC601
0x1400fc56d  mov     rdx, rbx
0x1400fc570  mov     rcx, rsi
0x1400fc573  call    NvmeAdapterQueryCoolingInterface
0x1400fc578  mov     edi, eax
0x1400fc57a  jmp     short loc_1400FC5A0
0x1400fc57c  mov     r8, [rsi+3F8h]
0x1400fc583  mov     rdx, rbx
0x1400fc586  call    PortQueryInterfaceFdoQdr
0x1400fc58b  jmp     short loc_1400FC599
0x1400fc58d  mov     r8, [rsi+20h]
0x1400fc591  mov     rdx, rbx
0x1400fc594  call    PortQueryInterfaceFdoInfo
0x1400fc599  mov     edi, eax
0x1400fc59b  mov     [rbx+30h], eax
0x1400fc59e  not     eax
0x1400fc5a0  shr     eax, 1Fh
0x1400fc5a3  test    al, al
0x1400fc5a5  jz      loc_1400FC4E0
0x1400fc5ab  cmp     cs:StorEtwLoggingEnabled, 0
0x1400fc5b2  jz      short loc_1400FC5EC
0x1400fc5b4  lea     rdx, [rsp+0C8h+var_58]
0x1400fc5b9  mov     rcx, rbx
0x1400fc5bc  call    cs:__imp_IoGetActivityIdIrp
0x1400fc5c3  nop     dword ptr [rax+rax+00h]
0x1400fc5c8  test    cs:byte_140177432, 20h
0x1400fc5cf  jz      short loc_1400FC5EC
0x1400fc5d1  mov     eax, [rbx+30h]
0x1400fc5d4  lea     r8, [rsp+0C8h+var_58]
0x1400fc5d9  mov     r9, rbx
0x1400fc5dc  mov     [rsp+0C8h+var_A8], eax
0x1400fc5e0  lea     rdx, EventPnpRequestComplete
0x1400fc5e7  call    McTemplateK0pd_EtwWriteTransfer
0x1400fc5ec  mov     rcx, [rsi+18h]
0x1400fc5f0  mov     rdx, rbx
0x1400fc5f3  call    RaForwardIrp
0x1400fc5f8  mov     edi, eax
0x1400fc5fa  jmp     loc_1400FC86A
0x1400fc5ff  xor     ecx, ecx
0x1400fc601  mov     eax, [rbx+30h]
0x1400fc604  lea     r8, [rsp+0C8h+var_68]
0x1400fc609  mov     [rsp+0C8h+var_A0], eax
0x1400fc60d  mov     r9, rbx
0x1400fc610  mov     [rsp+0C8h+var_A8], ecx
0x1400fc614  call    McTemplateK0pqd_EtwWriteTransfer
0x1400fc619  jmp     loc_1400FC859
0x1400fc61e  test    cs:byte_140177432, 20h
0x1400fc625  jz      loc_1400FC859
0x1400fc62b  lea     rdx, EventPnpRequestComplete
0x1400fc632  jmp     loc_1400FC845
0x1400fc637  cmp     cs:byte_140177431, 0
0x1400fc63e  jge     loc_1400FC859
0x1400fc644  mov     rdx, [rdx+8]
0x1400fc648  mov     r10d, 1
0x1400fc64e  movzx   eax, byte ptr [rdx+2]
0x1400fc652  cmp     al, 28h ; '('
0x1400fc654  jnz     loc_1400FC73D
0x1400fc65a  cmp     dword ptr [rdx+14h], 0
0x1400fc65e  jnz     loc_1400FC859
0x1400fc664  mov     r15d, [rdx+38h]
0x1400fc668  test    r15d, r15d
0x1400fc66b  jz      loc_1400FC859
0x1400fc671  xor     r11b, r11b
0x1400fc674  xor     esi, esi
0x1400fc676  xor     r12b, r12b
0x1400fc679  xor     r9d, r9d
0x1400fc67c  xor     r14d, r14d
0x1400fc67f  xor     r13b, r13b
0x1400fc682  mov     ecx, [rdx+r14*4+78h]
0x1400fc687  cmp     ecx, 80h
0x1400fc68d  jb      short loc_1400FC704
0x1400fc68f  mov     ebp, [rdx+10h]
0x1400fc692  cmp     ecx, ebp
0x1400fc694  jnb     short loc_1400FC704
0x1400fc696  mov     r8d, ecx
0x1400fc699  mov     ecx, [rcx+rdx]
0x1400fc69c  sub     ecx, 40h ; '@'
0x1400fc69f  jz      short loc_1400FC6F6
0x1400fc6a1  sub     ecx, r10d
0x1400fc6a4  jz      short loc_1400FC6CA
0x1400fc6a6  cmp     ecx, r10d
0x1400fc6a9  jnz     short loc_1400FC6FF
0x1400fc6ab  lea     rcx, [r8+28h]
0x1400fc6af  cmp     rcx, rbp
0x1400fc6b2  ja      short loc_1400FC6FF
0x1400fc6b4  cmp     dword ptr [r8+rdx+0Ch], 0
0x1400fc6ba  jbe     short loc_1400FC6C3
0x1400fc6bc  lea     rsi, [rdx+20h]
0x1400fc6c0  add     rsi, r8
0x1400fc6c3  mov     r9, [r8+rdx+18h]
0x1400fc6c8  jmp     short loc_1400FC726
0x1400fc6ca  lea     rcx, [r8+38h]
0x1400fc6ce  cmp     rcx, rbp
0x1400fc6d1  ja      short loc_1400FC6FF
0x1400fc6d3  cmp     byte ptr [r8+rdx+0Ah], 0
0x1400fc6d9  mov     r13b, r10b
0x1400fc6dc  jbe     short loc_1400FC6E5
0x1400fc6de  lea     rsi, [rdx+18h]
0x1400fc6e2  add     rsi, r8
0x1400fc6e5  mov     r12b, [r8+rdx+8]
0x1400fc6ea  mov     r9, [r8+rdx+10h]
0x1400fc6ef  mov     r11b, [r8+rdx+9]
0x1400fc6f4  jmp     short loc_1400FC6FF
0x1400fc6f6  lea     rcx, [r8+28h]
0x1400fc6fa  cmp     rcx, rbp
0x1400fc6fd  jbe     short loc_1400FC712
0x1400fc6ff  test    r13b, r13b
0x1400fc702  jnz     short loc_1400FC730
0x1400fc704  add     r14d, r10d
0x1400fc707  cmp     r14d, r15d
0x1400fc70a  jb      loc_1400FC682
0x1400fc710  jmp     short loc_1400FC730
0x1400fc712  cmp     byte ptr [r8+rdx+0Ah], 0
0x1400fc718  jbe     short loc_1400FC721
0x1400fc71a  lea     rsi, [rdx+18h]
0x1400fc71e  add     rsi, r8
0x1400fc721  mov     r9, [r8+rdx+10h]
0x1400fc726  mov     r11b, [r8+rdx+9]
0x1400fc72b  mov     r12b, [r8+rdx+8]
0x1400fc730  test    rsi, rsi
0x1400fc733  jz      loc_1400FC859
0x1400fc739  mov     cl, [rsi]
0x1400fc73b  jmp     short loc_1400FC754
0x1400fc73d  mov     cl, [rdx+48h]
0x1400fc740  mov     r9, [rdx+20h]
0x1400fc744  mov     r11b, [rdx+0Bh]
0x1400fc748  mov     r12b, [rdx+4]
0x1400fc74c  test    eax, eax
0x1400fc74e  jnz     loc_1400FC859
0x1400fc754  sub     cl, 8
0x1400fc757  test    cl, 5Dh
0x1400fc75a  jnz     loc_1400FC859
0x1400fc760  mov     bpl, [rdx+3]
0x1400fc764  cmp     bpl, r10b
0x1400fc767  jz      loc_1400FC7FA
0x1400fc76d  test    r9, r9
0x1400fc770  jz      loc_1400FC7FA
0x1400fc776  test    r11b, r11b
0x1400fc779  jz      short loc_1400FC7FA
0x1400fc77b  mov     al, [r9]
0x1400fc77e  xor     dl, dl
0x1400fc780  and     al, 7Fh
0x1400fc782  movzx   ecx, r11b
0x1400fc786  sub     al, 72h ; 'r'
0x1400fc788  xor     sil, sil
0x1400fc78b  xor     r8b, r8b
0x1400fc78e  add     rcx, r9
0x1400fc791  cmp     al, r10b
0x1400fc794  lea     rax, [r9+8]
0x1400fc798  jbe     short loc_1400FC7DC
0x1400fc79a  cmp     rax, rcx
0x1400fc79d  ja      short loc_1400FC7F2
0x1400fc79f  movzx   ecx, byte ptr [r9+7]
0x1400fc7a4  lea     r8, [r9+0Dh]
0x1400fc7a8  mov     dl, [r9+2]
0x1400fc7ac  add     ecx, 8
0x1400fc7af  and     dl, 0Fh
0x1400fc7b2  movzx   eax, r11b
0x1400fc7b6  cmp     ecx, eax
0x1400fc7b8  cmovbe  eax, ecx
0x1400fc7bb  mov     ecx, eax
0x1400fc7bd  add     rcx, r9
0x1400fc7c0  cmp     r8, rcx
0x1400fc7c3  ja      short loc_1400FC7C9
0x1400fc7c5  mov     sil, [r9+0Ch]
0x1400fc7c9  lea     rax, [r9+0Eh]
0x1400fc7cd  cmp     rax, rcx
0x1400fc7d0  ja      short loc_1400FC7D7
0x1400fc7d2  mov     r8b, [r8]
0x1400fc7d5  jmp     short loc_1400FC7F5
0x1400fc7d7  xor     r8b, r8b
0x1400fc7da  jmp     short loc_1400FC7F5
0x1400fc7dc  cmp     rax, rcx
0x1400fc7df  ja      short loc_1400FC7F2
0x1400fc7e1  mov     dl, [r9+1]
0x1400fc7e5  mov     sil, [r9+2]
0x1400fc7e9  and     dl, 0Fh
0x1400fc7ec  mov     r8b, [r9+3]
0x1400fc7f0  jmp     short loc_1400FC7F5
0x1400fc7f2  xor     r10b, r10b
0x1400fc7f5  test    r10b, r10b
0x1400fc7f8  jnz     short loc_1400FC802
0x1400fc7fa  xor     dl, dl
0x1400fc7fc  xor     sil, sil
0x1400fc7ff  xor     r8b, r8b
0x1400fc802  mov     eax, [rbx+30h]
0x1400fc805  mov     r9, rbx
0x1400fc808  mov     [rsp+0C8h+var_78], rbx
0x1400fc80d  mov     [rsp+0C8h+var_80], r8b
0x1400fc812  lea     r8, [rsp+0C8h+var_68]
0x1400fc817  mov     [rsp+0C8h+var_88], sil
0x1400fc81c  mov     [rsp+0C8h+var_90], dl
0x1400fc820  mov     [rsp+0C8h+var_98], r12b
0x1400fc825  mov     byte ptr [rsp+0C8h+var_A0], bpl
0x1400fc82a  mov     [rsp+0C8h+var_A8], eax
0x1400fc82e  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x1400fc833  jmp     short loc_1400FC859
0x1400fc835  test    cs:byte_140177432, 8
0x1400fc83c  jz      short loc_1400FC859
0x1400fc83e  lea     rdx, EventNonReadWriteRequestComplete
0x1400fc845  mov     eax, [rbx+30h]
0x1400fc848  lea     r8, [rsp+0C8h+var_68]
0x1400fc84d  mov     r9, rbx
0x1400fc850  mov     [rsp+0C8h+var_A8], eax
0x1400fc854  call    McTemplateK0pd_EtwWriteTransfer
0x1400fc859  xor     edx, edx; PriorityBoost
0x1400fc85b  mov     rcx, rbx; Irp
0x1400fc85e  call    cs:__imp_IofCompleteRequest
0x1400fc865  nop     dword ptr [rax+rax+00h]
0x1400fc86a  mov     eax, edi
0x1400fc86c  mov     rcx, [rsp+0C8h+var_48]
0x1400fc874  xor     rcx, rsp; StackCookie
  ... truncated ...
```
