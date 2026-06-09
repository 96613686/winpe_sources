# SpLogStatus(SP_DEVICE *,_IRP *)

- ea: `0x140022180`
- end: `0x1400224ee`
- name: `?SpLogStatus@@YAXPEAVSP_DEVICE@@PEAU_IRP@@@Z`
- size: `878`
- prototype: `void __fastcall(struct SP_DEVICE *, struct _IRP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140016080`

## callees

- `0x140022180`
- `0x14002fd40`
- `0x140067fc0`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x1400221bd`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400221bd`
- `ntoskrnl!EtwWriteTransfer` at `0x14002232e`
- `ntoskrnl!EtwWriteTransfer` at `0x1400224b9`
- `ntoskrnl!EtwWriteTransfer` at `0x14002232e`
- `ntoskrnl!EtwWriteTransfer` at `0x1400224b9`

## pseudocode

```c
void __fastcall SpLogStatus(struct SP_DEVICE *a1, struct _IRP *a2)
{
  __int64 v4; // rcx
  NTSTATUS Status; // r8d
  NTSTATUS v6; // [rsp+30h] [rbp-59h] BYREF
  __int64 v7; // [rsp+38h] [rbp-51h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-49h] BYREF
  EVENT_DESCRIPTOR v9; // [rsp+50h] [rbp-39h] BYREF
  GUID v10; // [rsp+60h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-19h] BYREF
  int *v12; // [rsp+80h] [rbp-9h]
  int v13; // [rsp+88h] [rbp-1h]
  int v14; // [rsp+8Ch] [rbp+3h]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+90h] [rbp+7h]
  __int64 v16; // [rsp+98h] [rbp+Fh]
  char *v17; // [rsp+A0h] [rbp+17h]
  __int64 v18; // [rsp+A8h] [rbp+1Fh]
  char *v19; // [rsp+B0h] [rbp+27h]
  __int64 v20; // [rsp+B8h] [rbp+2Fh]
  NTSTATUS *v21; // [rsp+C0h] [rbp+37h]
  __int64 v22; // [rsp+C8h] [rbp+3Fh]

  v10 = GUID_NULL;
  IoGetActivityIdIrp(a2, &v10);
  Status = a2->IoStatus.Status;
  if ( Status > -1070071807 )
  {
    if ( Status != -1070071804 && Status != -1070071755 && Status != -1070071728 )
      return;
    goto LABEL_18;
  }
  if ( Status == -1070071807 || Status == -1073741670 )
  {
LABEL_18:
    if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 1) != 0 )
      McTemplateK0jq_EtwWriteTransfer(v4, SpaceFTWriteFailure, &v10, (char *)a1 + 40, Status);
    if ( (unsigned int)dword_14007F050 > 5
      && (qword_14007F060 & 0x400000000000LL) != 0
      && (qword_14007F068 & 0x400000000000LL) == qword_14007F068 )
    {
      v6 = a2->IoStatus.Status;
      v17 = (char *)a1 + 24;
      v21 = &v6;
      v9.Keyword = 0x400000000000LL;
      v19 = (char *)a1 + 40;
      *(_QWORD *)&EventDescriptor.Id = 0x1000000;
      p_EventDescriptor = &EventDescriptor;
      *(_DWORD *)&v9.Level = 5;
      UserData.Ptr = (ULONGLONG)off_14007F058;
      v22 = 4;
      v20 = 16;
      v18 = 16;
      v16 = 8;
      *(_DWORD *)&v9.Id = 184549376;
      UserData.Size = *(unsigned __int16 *)off_14007F058;
      v12 = (int *)&byte_14007593F;
      UserData.Reserved = 2;
      v13 = 77;
      v14 = 1;
      LODWORD(v7) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &v9, 0, 0, 6u, &UserData);
    }
    a2->IoStatus.Status = -1073740693;
    return;
  }
  if ( Status != -1073740703 )
  {
    if ( Status != -1073740693 )
    {
      if ( Status == -1073740692 )
      {
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 1) != 0 )
          McTemplateK0jq_EtwWriteTransfer(v4, SpaceDIScanRequired, &v10, (char *)a1 + 40, -1073740692);
        if ( (unsigned int)dword_14007F050 > 5
          && (qword_14007F060 & 0x400000000000LL) != 0
          && (qword_14007F068 & 0x400000000000LL) == qword_14007F068 )
        {
          EventDescriptor.Keyword = 0x400000000000LL;
          v17 = (char *)a1 + 24;
          v19 = (char *)a1 + 40;
          v7 = 0x1000000;
          p_EventDescriptor = (EVENT_DESCRIPTOR *)&v7;
          *(_DWORD *)&EventDescriptor.Level = 5;
          UserData.Ptr = (ULONGLONG)off_14007F058;
          v20 = 16;
          v18 = 16;
          v16 = 8;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          UserData.Size = *(unsigned __int16 *)off_14007F058;
          v12 = &dword_140075A14;
          UserData.Reserved = 2;
          v13 = 69;
          v14 = 1;
          v6 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
        }
      }
      return;
    }
    goto LABEL_18;
  }
  if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 1) != 0 )
    McTemplateK0jq_EtwWriteTransfer(v4, SpaceCapacityExhausted, &v10, (char *)a1 + 40, -1073740703);
}

```

## disassembly

```asm
0x140022180  mov     [rsp-8+arg_10], rbx
0x140022185  mov     [rsp-8+arg_18], rdi
0x14002218a  push    rbp
0x14002218b  lea     rbp, [rsp-57h]
0x140022190  sub     rsp, 0E0h
0x140022197  mov     rax, cs:__security_cookie
0x14002219e  xor     rax, rsp
0x1400221a1  mov     [rbp+57h+var_10], rax
0x1400221a5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400221ac  mov     rdi, rdx
0x1400221af  mov     rbx, rcx
0x1400221b2  lea     rdx, [rbp+57h+var_80]
0x1400221b6  mov     rcx, rdi
0x1400221b9  movups  [rbp+57h+var_80], xmm0
0x1400221bd  call    cs:__imp_IoGetActivityIdIrp
0x1400221c4  nop     dword ptr [rax+rax+00h]
0x1400221c9  mov     r8d, [rdi+30h]
0x1400221cd  cmp     r8d, 0C0380001h
0x1400221d4  jg      loc_14002236D
0x1400221da  jz      loc_14002238C
0x1400221e0  cmp     r8d, 0C000009Ah
0x1400221e7  jz      loc_14002238C
0x1400221ed  cmp     r8d, 0C0000461h
0x1400221f4  jz      loc_14002233F
0x1400221fa  cmp     r8d, 0C000046Bh
0x140022201  jz      loc_14002238C
0x140022207  cmp     r8d, 0C000046Ch
0x14002220e  jnz     loc_1400224CC
0x140022214  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 1
0x14002221b  jz      short loc_140022239
0x14002221d  lea     r9, [rbx+28h]
0x140022221  mov     [rsp+0E0h+UserDataCount], 0C000046Ch
0x140022229  lea     r8, [rbp+57h+var_80]
0x14002222d  lea     rdx, SpaceDIScanRequired
0x140022234  call    McTemplateK0jq_EtwWriteTransfer
0x140022239  mov     eax, cs:dword_14007F050
0x14002223f  cmp     eax, 5
0x140022242  jbe     loc_1400224CC
0x140022248  mov     rcx, cs:qword_14007F068
0x14002224f  mov     rdx, 400000000000h
0x140022259  mov     rax, cs:qword_14007F060
0x140022260  test    rdx, rax
0x140022263  jz      loc_1400224CC
0x140022269  mov     rax, rcx
0x14002226c  and     rax, rdx
0x14002226f  cmp     rax, rcx
0x140022272  jnz     loc_1400224CC
0x140022278  mov     [rbp+57h+EventDescriptor.Keyword], rdx
0x14002227c  lea     rcx, [rbx+18h]
0x140022280  lea     rax, [rcx+10h]
0x140022284  mov     [rbp+57h+var_40], rcx
0x140022288  mov     [rbp+57h+var_30], rax
0x14002228c  lea     rcx, _TraceLoggingMetadata
0x140022293  lea     rax, [rbp+57h+var_A8]
0x140022297  mov     [rbp+57h+var_A8], 1000000h
0x14002229f  mov     [rbp+57h+var_50], rax
0x1400222a3  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1400222a7  movzx   eax, cs:word_140075A0A
0x1400222ae  xor     r9d, r9d; RelatedActivityId
0x1400222b1  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1400222b4  xor     r8d, r8d; ActivityId
0x1400222b7  mov     rax, cs:off_14007F058
0x1400222be  mov     [rbp+57h+var_70.Ptr], rax
0x1400222c2  mov     [rbp+57h+var_28], 10h
0x1400222ca  mov     [rbp+57h+var_38], 10h
0x1400222d2  mov     [rbp+57h+var_48], 8
0x1400222da  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1400222e1  movzx   eax, word ptr [rax]
0x1400222e4  mov     [rbp+57h+var_70.Size], eax
0x1400222e7  lea     rax, dword_140075A14
0x1400222ee  mov     [rbp+57h+var_60], rax
0x1400222f2  lea     rax, _TraceLoggingMetadataEnd
0x1400222f9  sub     eax, ecx
0x1400222fb  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x140022302  mov     [rbp+57h+var_58], 45h ; 'E'
0x140022309  mov     [rbp+57h+var_54], 1
0x140022310  mov     [rbp+57h+var_B0], eax
0x140022313  mov     eax, [rbp+57h+var_B0]
0x140022316  mov     rcx, cs:RegHandle; RegHandle
0x14002231d  lea     rax, [rbp+57h+var_70]
0x140022321  mov     [rsp+0E0h+UserData], rax; UserData
0x140022326  mov     [rsp+0E0h+UserDataCount], 5; UserDataCount
0x14002232e  call    cs:__imp_EtwWriteTransfer
0x140022335  nop     dword ptr [rax+rax+00h]
0x14002233a  jmp     loc_1400224CC
0x14002233f  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 1
0x140022346  jz      loc_1400224CC
0x14002234c  lea     r9, [rbx+28h]
0x140022350  mov     [rsp+0E0h+UserDataCount], 0C0000461h
0x140022358  lea     r8, [rbp+57h+var_80]
0x14002235c  lea     rdx, SpaceCapacityExhausted
0x140022363  call    McTemplateK0jq_EtwWriteTransfer
0x140022368  jmp     loc_1400224CC
0x14002236d  cmp     r8d, 0C0380004h
0x140022374  jz      short loc_14002238C
0x140022376  cmp     r8d, 0C0380035h
0x14002237d  jz      short loc_14002238C
0x14002237f  cmp     r8d, 0C0380050h
0x140022386  jnz     loc_1400224CC
0x14002238c  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 1
0x140022393  jz      short loc_1400223AE
0x140022395  mov     [rsp+0E0h+UserDataCount], r8d
0x14002239a  lea     r9, [rbx+28h]
0x14002239e  lea     r8, [rbp+57h+var_80]
0x1400223a2  lea     rdx, SpaceFTWriteFailure
0x1400223a9  call    McTemplateK0jq_EtwWriteTransfer
0x1400223ae  mov     eax, cs:dword_14007F050
0x1400223b4  cmp     eax, 5
0x1400223b7  jbe     loc_1400224C5
0x1400223bd  mov     rcx, cs:qword_14007F068
0x1400223c4  mov     rdx, 400000000000h
0x1400223ce  mov     rax, cs:qword_14007F060
0x1400223d5  test    rdx, rax
0x1400223d8  jz      loc_1400224C5
0x1400223de  mov     rax, rcx
0x1400223e1  and     rax, rdx
0x1400223e4  cmp     rax, rcx
0x1400223e7  jnz     loc_1400224C5
0x1400223ed  mov     eax, [rdi+30h]
0x1400223f0  lea     rcx, [rbx+18h]
0x1400223f4  mov     [rbp+57h+var_B0], eax
0x1400223f7  xor     r9d, r9d; RelatedActivityId
0x1400223fa  mov     [rbp+57h+var_40], rcx
0x1400223fe  lea     rax, [rbp+57h+var_B0]
0x140022402  mov     [rbp+57h+var_20], rax
0x140022406  xor     r8d, r8d; ActivityId
0x140022409  lea     rax, [rcx+10h]
0x14002240d  mov     [rbp+57h+var_90.Keyword], rdx
0x140022411  mov     [rbp+57h+var_30], rax
0x140022415  lea     rcx, _TraceLoggingMetadata
0x14002241c  lea     rax, [rbp+57h+EventDescriptor]
0x140022420  mov     qword ptr [rbp+57h+EventDescriptor.Id], 1000000h
0x140022428  mov     [rbp+57h+var_50], rax
0x14002242c  lea     rdx, [rbp+57h+var_90]; EventDescriptor
0x140022430  movzx   eax, cs:word_140075935
0x140022437  mov     dword ptr [rbp+57h+var_90.Level], eax
0x14002243a  mov     rax, cs:off_14007F058
0x140022441  mov     [rbp+57h+var_70.Ptr], rax
0x140022445  mov     [rbp+57h+var_18], 4
0x14002244d  mov     [rbp+57h+var_28], 10h
0x140022455  mov     [rbp+57h+var_38], 10h
0x14002245d  mov     [rbp+57h+var_48], 8
0x140022465  mov     dword ptr [rbp+57h+var_90.Id], 0B000000h
0x14002246c  movzx   eax, word ptr [rax]
0x14002246f  mov     [rbp+57h+var_70.Size], eax
0x140022472  lea     rax, byte_14007593F
0x140022479  mov     [rbp+57h+var_60], rax
0x14002247d  lea     rax, _TraceLoggingMetadataEnd
0x140022484  sub     eax, ecx
0x140022486  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x14002248d  mov     [rbp+57h+var_58], 4Dh ; 'M'
0x140022494  mov     [rbp+57h+var_54], 1
0x14002249b  mov     dword ptr [rbp+57h+var_A8], eax
0x14002249e  mov     eax, dword ptr [rbp+57h+var_A8]
0x1400224a1  mov     rcx, cs:RegHandle; RegHandle
0x1400224a8  lea     rax, [rbp+57h+var_70]
0x1400224ac  mov     [rsp+0E0h+UserData], rax; UserData
0x1400224b1  mov     [rsp+0E0h+UserDataCount], 6; UserDataCount
0x1400224b9  call    cs:__imp_EtwWriteTransfer
0x1400224c0  nop     dword ptr [rax+rax+00h]
0x1400224c5  mov     dword ptr [rdi+30h], 0C000046Bh
0x1400224cc  mov     rcx, [rbp+57h+var_10]
0x1400224d0  xor     rcx, rsp; StackCookie
0x1400224d3  call    __security_check_cookie
0x1400224d8  lea     r11, [rsp+0E0h+var_s0]
0x1400224e0  mov     rbx, [r11+20h]
0x1400224e4  mov     rdi, [r11+28h]
0x1400224e8  mov     rsp, r11
0x1400224eb  pop     rbp
0x1400224ec  retn
```
