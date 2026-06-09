# CConnectedAccounts::_Init(void)

- ea: `0x18000ad20`
- end: `0x18000b27d`
- name: `?_Init@CConnectedAccounts@@AEAAJXZ`
- size: `1373`
- prototype: `__int64 __fastcall(CConnectedAccounts *__hidden this)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000aa70`
- `0x180014a90`
- `0x180014b10`
- `0x180014b50`

## callees

- `0x180008300`
- `0x180008c10`
- `0x18000ad20`
- `0x18000c240`
- `0x180017010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b06c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b144`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b223`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b06c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b144`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b223`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000add8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000add8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ad71`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ad71`

## pseudocode

```c
HRESULT __fastcall CConnectedAccounts::_Init(CConnectedAccounts *this)
{
  __int64 *v2; // r14
  HRESULT result; // eax
  LSTATUS ValueW; // eax
  bool v5; // sf
  __int64 v6; // rdx
  __int64 v7; // rcx
  signed int v8; // edi
  HDPA v9; // rax
  int v10; // ebx
  int *v11; // rax
  DWORD *v12; // rax
  DWORD v13; // ecx
  unsigned int *v14; // rax
  unsigned int v15; // ecx
  __int64 v16; // rcx
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v18; // [rsp+44h] [rbp-BCh] BYREF
  EVENT_DESCRIPTOR p; // [rsp+48h] [rbp-B8h] BYREF
  int pvData; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+68h] [rbp-98h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-90h] BYREF
  __int16 *v24; // [rsp+80h] [rbp-80h]
  int v25; // [rsp+88h] [rbp-78h]
  int v26; // [rsp+8Ch] [rbp-74h]
  DWORD *p_pcbData; // [rsp+90h] [rbp-70h]
  __int64 v28; // [rsp+98h] [rbp-68h]
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+A0h] [rbp-60h] BYREF
  char *v30; // [rsp+B0h] [rbp-50h]
  int v31; // [rsp+B8h] [rbp-48h]
  int v32; // [rsp+BCh] [rbp-44h]
  DWORD *p_p; // [rsp+C0h] [rbp-40h]
  __int64 v34; // [rsp+C8h] [rbp-38h]
  unsigned int *v35; // [rsp+D0h] [rbp-30h]
  __int64 v36; // [rsp+D8h] [rbp-28h]

  if ( *((_BYTE *)this + 32) )
    return 1;
  v2 = (__int64 *)((char *)this + 24);
  result = CoCreateInstance(
             &GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e,
             0,
             1u,
             &GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1,
             (LPVOID *)this + 3);
  if ( result >= 0 )
  {
    v22 = 0;
    pvData = 0;
    pcbData = 4;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"System\\CurrentControlSet\\Control\\SafeBoot\\Option",
               L"OptionValue",
               0x10u,
               0,
               &pvData,
               &pcbData);
    v5 = ValueW < 0;
    if ( ValueW > 0 )
      v5 = 1;
    if ( v5 || (v6 = 0, (unsigned int)(pvData - 1) > 1) )
      v6 = 1;
    v7 = *v2;
    pvData = v6;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v7 + 24LL))(v7, v6, 0, &v22);
    if ( v8 < 0 )
    {
      if ( (unsigned int)dword_18001F000 > 4 )
      {
        *(_DWORD *)&p.Id = v8;
        p_p = (DWORD *)&p;
        v29.Ptr = (ULONGLONG)off_18001F008;
        v34 = 4;
        UserData.Ptr = 0x40B000000LL;
        *(_QWORD *)&UserData.Size = 0;
        v29.Size = *(unsigned __int16 *)off_18001F008;
        v30 = &byte_18001B56F;
        v29.Reserved = 2;
        v31 = 36;
        v32 = 1;
        v18 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 3u, &v29);
      }
    }
    else
    {
      v9 = g_pfn_DPA_Create(5);
      *((_QWORD *)this + 2) = v9;
      if ( v9 )
      {
        v8 = 0;
        while ( 1 )
        {
          v21 = 0;
          *(_QWORD *)&p.Id = 0;
          pcbData = 0;
          if ( (*(unsigned int (__fastcall **)(__int64, __int64, EVENT_DESCRIPTOR *, DWORD *))(*(_QWORD *)v22 + 24LL))(
                 v22,
                 1,
                 &p,
                 &pcbData) )
          {
            break;
          }
          v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&p.Id)(
                  *(_QWORD *)&p.Id,
                  &GUID_9d5f2149_de8c_45f2_b313_6587a04f771d,
                  &v21);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&p.Id + 16LL))(*(_QWORD *)&p.Id);
          if ( v10 < 0 )
            break;
          *(_QWORD *)&p.Id = 0;
          v8 = (*(__int64 (__fastcall **)(__int64, EVENT_DESCRIPTOR *))(*(_QWORD *)v21 + 24LL))(v21, &p);
          if ( v8 >= 0 )
          {
            v24 = 0;
            UserData = 0;
            LOWORD(UserData.Ptr) = 11;
            LOWORD(UserData.Size) = -1;
            (*(void (__fastcall **)(_QWORD, __int128 *, struct _EVENT_DATA_DESCRIPTOR *))(**(_QWORD **)&p.Id + 48LL))(
              *(_QWORD *)&p.Id,
              &PKEY_SAM_DontEnumerateForLogon,
              &UserData);
            if ( DPA_InsertPtr(*((HDPA *)this + 2), 0x7FFFFFFF, *(void **)&p.Id) == -1 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&p.Id + 16LL))(*(_QWORD *)&p.Id);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        if ( v8 >= 0 && (v11 = (int *)*((_QWORD *)this + 2)) != 0 && *v11 > 0 )
        {
          *((_BYTE *)this + 32) = 1;
          if ( (unsigned int)dword_18001F000 > 4 )
          {
            v12 = (DWORD *)*((_QWORD *)this + 2);
            if ( v12 )
              v13 = *v12;
            else
              v13 = 0;
            pcbData = v13;
            p_pcbData = &pcbData;
            UserData.Ptr = (ULONGLONG)off_18001F008;
            v28 = 4;
            *(_QWORD *)&p.Id = 0x40B000000LL;
            p.Keyword = 0;
            UserData.Size = *(unsigned __int16 *)off_18001F008;
            v24 = word_18001B5EA;
            UserData.Reserved = 2;
            v25 = 61;
            v26 = 1;
            v18 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(RegHandle, &p, 0, 0, 3u, &UserData);
          }
        }
        else
        {
          if ( (unsigned int)dword_18001F000 > 4 )
          {
            v14 = (unsigned int *)*((_QWORD *)this + 2);
            if ( v14 )
              v15 = *v14;
            else
              v15 = 0;
            v18 = v15;
            v35 = &v18;
            pcbData = v8;
            p_p = &pcbData;
            v29.Ptr = (ULONGLONG)off_18001F008;
            v36 = 4;
            v34 = 4;
            UserData.Ptr = 0x40B000000LL;
            *(_QWORD *)&UserData.Size = 0;
            v29.Size = *(unsigned __int16 *)off_18001F008;
            v30 = &byte_18001B59F;
            v29.Reserved = 2;
            v31 = 63;
            v32 = 1;
            *(_DWORD *)&p.Id = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 4u, &v29);
          }
          (*(void (__fastcall **)(CConnectedAccounts *))(*(_QWORD *)this + 48LL))(this);
          v8 = -2147467259;
        }
      }
      else
      {
        v8 = -2147024882;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    if ( !*((_BYTE *)this + 32) )
    {
      v16 = *v2;
      *v2 = 0;
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18000ad20  push    rbp
0x18000ad22  push    rsi
0x18000ad23  lea     rbp, [rsp-8]
0x18000ad28  sub     rsp, 108h
0x18000ad2f  mov     rax, cs:__security_cookie
0x18000ad36  xor     rax, rsp
0x18000ad39  mov     [rbp+10h+var_30], rax
0x18000ad3d  cmp     byte ptr [rcx+20h], 0
0x18000ad41  mov     rsi, rcx
0x18000ad44  jnz     loc_18000B276
0x18000ad4a  mov     [rsp+110h+var_18], r14
0x18000ad52  lea     r9, _GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1; riid
0x18000ad59  lea     r14, [rcx+18h]
0x18000ad5d  xor     edx, edx; pUnkOuter
0x18000ad5f  lea     rcx, _GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e; rclsid
0x18000ad66  mov     [rsp+110h+ppv], r14; ppv
0x18000ad6b  mov     r8d, 1; dwClsContext
0x18000ad71  call    cs:__imp_CoCreateInstance
0x18000ad77  test    eax, eax
0x18000ad79  js      loc_18000B258
0x18000ad7f  lea     rax, [rsp+110h+var_D0]
0x18000ad84  mov     [rsp+110h+arg_10], rdi
0x18000ad8c  mov     [rsp+110h+pcbData], rax; pcbData
0x18000ad91  lea     r8, aOptionvalue; "OptionValue"
0x18000ad98  lea     rax, [rsp+110h+var_B8]
0x18000ad9d  mov     [rsp+110h+var_20], r15
0x18000ada5  xor     r15d, r15d
0x18000ada8  mov     [rsp+110h+pvData], rax; pvData
0x18000adad  mov     r9d, 10h; dwFlags
0x18000adb3  mov     [rsp+110h+ppv], r15; pdwType
0x18000adb8  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Saf"...
0x18000adbf  mov     [rsp+110h+var_A8], r15
0x18000adc4  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000adcb  mov     [rsp+110h+var_B8], r15d
0x18000add0  mov     [rsp+110h+var_D0], 4
0x18000add8  call    cs:__imp_RegGetValueW
0x18000adde  test    eax, eax
0x18000ade0  jle     short loc_18000ADEC
0x18000ade2  movzx   eax, ax
0x18000ade5  or      eax, 80070000h
0x18000adea  test    eax, eax
0x18000adec  js      short loc_18000ADFC
0x18000adee  mov     eax, [rsp+110h+var_B8]
0x18000adf2  mov     edx, r15d
0x18000adf5  dec     eax
0x18000adf7  cmp     eax, 1
0x18000adfa  jbe     short loc_18000AE01
0x18000adfc  mov     edx, 1
0x18000ae01  mov     rcx, [r14]
0x18000ae04  lea     r9, [rsp+110h+var_A8]
0x18000ae09  mov     [rsp+110h+var_B8], edx
0x18000ae0d  xor     r8d, r8d
0x18000ae10  mov     rax, [rcx]
0x18000ae13  mov     rax, [rax+18h]
0x18000ae17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae1c  mov     edi, eax
0x18000ae1e  test    eax, eax
0x18000ae20  js      loc_18000B17B
0x18000ae26  mov     ecx, 5; cItemGrow
0x18000ae2b  call    cs:g_pfn_DPA_Create
0x18000ae31  mov     [rsi+10h], rax
0x18000ae35  test    rax, rax
0x18000ae38  jz      loc_18000B160
0x18000ae3e  mov     [rsp+110h+arg_18], r12
0x18000ae46  mov     edi, r15d
0x18000ae49  mov     [rsp+110h+var_10], r13
0x18000ae51  mov     r12d, 0Bh
0x18000ae57  mov     r13d, 0FFFFFFFFh
0x18000ae5d  mov     [rsp+110h+arg_8], rbx
0x18000ae65  nop     word ptr [rax+rax+00000000h]
0x18000ae70  mov     rcx, [rsp+110h+var_A8]
0x18000ae75  lea     r9, [rsp+110h+var_D0]
0x18000ae7a  mov     [rsp+110h+var_B0], r15
0x18000ae7f  lea     r8, [rsp+110h+p]
0x18000ae84  mov     edx, 1
0x18000ae89  mov     [rsp+110h+p], r15
0x18000ae8e  mov     [rsp+110h+var_D0], r15d
0x18000ae93  mov     rax, [rcx]
0x18000ae96  mov     rax, [rax+18h]
0x18000ae9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae9f  test    eax, eax
0x18000aea1  jnz     loc_18000AF76
0x18000aea7  mov     rcx, [rsp+110h+p]
0x18000aeac  lea     r8, [rsp+110h+var_B0]
0x18000aeb1  lea     rdx, _GUID_9d5f2149_de8c_45f2_b313_6587a04f771d
0x18000aeb8  mov     rax, [rcx]
0x18000aebb  mov     rax, [rax]
0x18000aebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aec3  mov     rcx, [rsp+110h+p]
0x18000aec8  mov     ebx, eax
0x18000aeca  mov     rax, [rcx]
0x18000aecd  mov     rax, [rax+10h]
0x18000aed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aed6  test    ebx, ebx
0x18000aed8  js      loc_18000AF76
0x18000aede  mov     rcx, [rsp+110h+var_B0]
0x18000aee3  lea     rdx, [rsp+110h+p]
0x18000aee8  mov     [rsp+110h+p], r15
0x18000aeed  mov     rax, [rcx]
0x18000aef0  mov     rax, [rax+18h]
0x18000aef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aef9  mov     edi, eax
0x18000aefb  test    eax, eax
0x18000aefd  js      short loc_18000AF60
0x18000aeff  mov     rcx, [rsp+110h+p]
0x18000af04  lea     r8, [rsp+110h+UserData]
0x18000af09  xor     eax, eax
0x18000af0b  lea     rdx, PKEY_SAM_DontEnumerateForLogon
0x18000af12  mov     [rbp+10h+var_90], rax
0x18000af16  xorps   xmm0, xmm0
0x18000af19  movups  xmmword ptr [rsp+110h+UserData.Ptr], xmm0
0x18000af1e  mov     word ptr [rsp+110h+UserData.Ptr], r12w
0x18000af24  mov     word ptr [rsp+110h+UserData.Size], r13w
0x18000af2a  mov     rax, [rcx]
0x18000af2d  mov     rax, [rax+30h]
0x18000af31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af36  mov     r8, [rsp+110h+p]; p
0x18000af3b  mov     edx, 7FFFFFFFh; i
0x18000af40  mov     rcx, [rsi+10h]; hdpa
0x18000af44  call    cs:__imp_DPA_InsertPtr
0x18000af4a  cmp     eax, r13d
0x18000af4d  jnz     short loc_18000AF60
0x18000af4f  mov     rcx, [rsp+110h+p]
0x18000af54  mov     rax, [rcx]
0x18000af57  mov     rax, [rax+10h]
0x18000af5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af60  mov     rcx, [rsp+110h+var_B0]
0x18000af65  mov     rax, [rcx]
0x18000af68  mov     rax, [rax+10h]
0x18000af6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af71  jmp     loc_18000AE70
0x18000af76  mov     r13, [rsp+110h+var_10]
0x18000af7e  mov     r12, [rsp+110h+arg_18]
0x18000af86  mov     rbx, [rsp+110h+arg_8]
0x18000af8e  test    edi, edi
0x18000af90  js      loc_18000B077
0x18000af96  mov     rax, [rsi+10h]
0x18000af9a  test    rax, rax
0x18000af9d  jz      loc_18000B077
0x18000afa3  cmp     [rax], r15d
0x18000afa6  jle     loc_18000B077
0x18000afac  mov     byte ptr [rsi+20h], 1
0x18000afb0  mov     eax, cs:dword_18001F000
0x18000afb6  cmp     eax, 4
0x18000afb9  jbe     loc_18000B165
0x18000afbf  mov     rax, [rsi+10h]
0x18000afc3  test    rax, rax
0x18000afc6  jz      short loc_18000AFCC
0x18000afc8  mov     ecx, [rax]
0x18000afca  jmp     short loc_18000AFCF
0x18000afcc  mov     ecx, r15d
0x18000afcf  mov     [rsp+110h+var_D0], ecx
0x18000afd3  lea     rax, [rsp+110h+var_D0]
0x18000afd8  mov     [rbp+10h+var_80], rax
0x18000afdc  lea     rcx, _TraceLoggingMetadata
0x18000afe3  movzx   eax, cs:word_18001B5E0
0x18000afea  lea     rdx, [rsp+110h+p]; EventDescriptor
0x18000afef  mov     dword ptr [rsp+110h+p+4], eax
0x18000aff3  xor     r9d, r9d; RelatedActivityId
0x18000aff6  mov     rax, cs:off_18001F008
0x18000affd  xor     r8d, r8d; ActivityId
0x18000b000  mov     [rsp+110h+UserData.Ptr], rax
0x18000b005  mov     [rbp+10h+var_78], 4
0x18000b00d  mov     dword ptr [rsp+110h+p], 0B000000h
0x18000b015  mov     [rsp+110h+var_C0], r15
0x18000b01a  movzx   eax, word ptr [rax]
0x18000b01d  mov     [rsp+110h+UserData.Size], eax
0x18000b021  lea     rax, word_18001B5EA
0x18000b028  mov     [rbp+10h+var_90], rax
0x18000b02c  lea     rax, _TraceLoggingMetadataEnd
0x18000b033  sub     eax, ecx
0x18000b035  mov     dword ptr [rsp+110h+UserData.0Ch], 2
0x18000b03d  mov     [rbp+10h+var_88], 3Dh ; '='
0x18000b044  mov     [rbp+10h+var_84], 1
0x18000b04b  mov     [rsp+110h+var_CC], eax
0x18000b04f  mov     eax, [rsp+110h+var_CC]
0x18000b053  mov     rcx, cs:RegHandle; RegHandle
0x18000b05a  lea     rax, [rsp+110h+UserData]
0x18000b05f  mov     [rsp+110h+pvData], rax; UserData
0x18000b064  mov     dword ptr [rsp+110h+ppv], 3; UserDataCount
0x18000b06c  call    cs:__imp_EventWriteTransfer
0x18000b072  jmp     loc_18000B165
0x18000b077  mov     eax, cs:dword_18001F000
0x18000b07d  cmp     eax, 4
0x18000b080  jbe     loc_18000B14A
0x18000b086  mov     rax, [rsi+10h]
0x18000b08a  test    rax, rax
0x18000b08d  jz      short loc_18000B093
0x18000b08f  mov     ecx, [rax]
0x18000b091  jmp     short loc_18000B096
0x18000b093  mov     ecx, r15d
0x18000b096  mov     [rsp+110h+var_CC], ecx
0x18000b09a  lea     rax, [rsp+110h+var_CC]
0x18000b09f  mov     [rbp+10h+var_40], rax
0x18000b0a3  lea     rcx, _TraceLoggingMetadata
0x18000b0aa  lea     rax, [rsp+110h+var_D0]
0x18000b0af  mov     [rsp+110h+var_D0], edi
0x18000b0b3  mov     [rbp+10h+var_50], rax
0x18000b0b7  lea     rdx, [rsp+110h+UserData]; EventDescriptor
0x18000b0bc  movzx   eax, cs:word_18001B595
0x18000b0c3  xor     r9d, r9d; RelatedActivityId
0x18000b0c6  mov     dword ptr [rsp+110h+UserData.Ptr+4], eax
0x18000b0ca  xor     r8d, r8d; ActivityId
0x18000b0cd  mov     rax, cs:off_18001F008
0x18000b0d4  mov     [rbp+10h+var_70.Ptr], rax
0x18000b0d8  mov     [rbp+10h+var_38], 4
0x18000b0e0  mov     [rbp+10h+var_48], 4
0x18000b0e8  mov     dword ptr [rsp+110h+UserData.Ptr], 0B000000h
0x18000b0f0  mov     qword ptr [rsp+110h+UserData.Size], r15
0x18000b0f5  movzx   eax, word ptr [rax]
0x18000b0f8  mov     [rbp+10h+var_70.Size], eax
0x18000b0fb  lea     rax, byte_18001B59F
0x18000b102  mov     [rbp+10h+var_60], rax
0x18000b106  lea     rax, _TraceLoggingMetadataEnd
0x18000b10d  sub     eax, ecx
0x18000b10f  mov     dword ptr [rbp+10h+var_70.0Ch], 2
0x18000b116  mov     [rbp+10h+var_58], 3Fh ; '?'
0x18000b11d  mov     [rbp+10h+var_54], 1
0x18000b124  mov     dword ptr [rsp+110h+p], eax
0x18000b128  mov     eax, dword ptr [rsp+110h+p]
0x18000b12c  mov     rcx, cs:RegHandle; RegHandle
0x18000b133  lea     rax, [rbp+10h+var_70]
0x18000b137  mov     [rsp+110h+pvData], rax; UserData
0x18000b13c  mov     dword ptr [rsp+110h+ppv], 4; UserDataCount
0x18000b144  call    cs:__imp_EventWriteTransfer
0x18000b14a  mov     rax, [rsi]
0x18000b14d  mov     rcx, rsi
0x18000b150  mov     rax, [rax+30h]
0x18000b154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b159  mov     edi, 80004005h
0x18000b15e  jmp     short loc_18000B165
0x18000b160  mov     edi, 8007000Eh
0x18000b165  mov     rcx, [rsp+110h+var_A8]
0x18000b16a  mov     rax, [rcx]
0x18000b16d  mov     rax, [rax+10h]
0x18000b171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b176  jmp     loc_18000B229
0x18000b17b  mov     eax, cs:dword_18001F000
0x18000b181  cmp     eax, 4
0x18000b184  jbe     loc_18000B229
0x18000b18a  lea     rax, [rsp+110h+p]
0x18000b18f  mov     dword ptr [rsp+110h+p], edi
0x18000b193  mov     [rbp+10h+var_50], rax
0x18000b197  lea     rcx, _TraceLoggingMetadata
0x18000b19e  movzx   eax, cs:word_18001B565
0x18000b1a5  lea     rdx, [rsp+110h+UserData]; EventDescriptor
0x18000b1aa  mov     dword ptr [rsp+110h+UserData.Ptr+4], eax
0x18000b1ae  xor     r9d, r9d; RelatedActivityId
0x18000b1b1  mov     rax, cs:off_18001F008
0x18000b1b8  xor     r8d, r8d; ActivityId
0x18000b1bb  mov     [rbp+10h+var_70.Ptr], rax
0x18000b1bf  mov     [rbp+10h+var_48], 4
0x18000b1c7  mov     dword ptr [rsp+110h+UserData.Ptr], 0B000000h
0x18000b1cf  mov     qword ptr [rsp+110h+UserData.Size], r15
0x18000b1d4  movzx   eax, word ptr [rax]
0x18000b1d7  mov     [rbp+10h+var_70.Size], eax
0x18000b1da  lea     rax, byte_18001B56F
0x18000b1e1  mov     [rbp+10h+var_60], rax
0x18000b1e5  lea     rax, _TraceLoggingMetadataEnd
0x18000b1ec  sub     eax, ecx
0x18000b1ee  mov     dword ptr [rbp+10h+var_70.0Ch], 2
0x18000b1f5  mov     [rbp+10h+var_58], 24h ; '$'
0x18000b1fc  mov     [rbp+10h+var_54], 1
0x18000b203  mov     [rsp+110h+var_CC], eax
0x18000b207  mov     eax, [rsp+110h+var_CC]
0x18000b20b  mov     rcx, cs:RegHandle; RegHandle
0x18000b212  lea     rax, [rbp+10h+var_70]
0x18000b216  mov     [rsp+110h+pvData], rax; UserData
0x18000b21b  mov     dword ptr [rsp+110h+ppv], 3; UserDataCount
0x18000b223  call    cs:__imp_EventWriteTransfer
0x18000b229  cmp     [rsi+20h], r15b
0x18000b22d  jnz     short loc_18000B246
0x18000b22f  mov     rcx, [r14]
0x18000b232  mov     [r14], r15
0x18000b235  test    rcx, rcx
0x18000b238  jz      short loc_18000B246
0x18000b23a  mov     rax, [rcx]
0x18000b23d  mov     rax, [rax+10h]
0x18000b241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b246  mov     r15, [rsp+110h+var_20]
0x18000b24e  mov     eax, edi
0x18000b250  mov     rdi, [rsp+110h+arg_10]
0x18000b258  mov     r14, [rsp+110h+var_18]
0x18000b260  mov     rcx, [rbp+10h+var_30]
0x18000b264  xor     rcx, rsp; StackCookie
0x18000b267  call    __security_check_cookie
0x18000b26c  add     rsp, 108h
0x18000b273  pop     rsi
0x18000b274  pop     rbp
0x18000b275  retn
0x18000b276  mov     eax, 1
0x18000b27b  jmp     short loc_18000B260
```
