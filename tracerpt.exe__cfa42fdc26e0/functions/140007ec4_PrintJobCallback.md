# PrintJobCallback

- ea: `0x140007ec4`
- end: `0x14000843e`
- name: `PrintJobCallback`
- size: `1402`
- prototype: `unsigned __int64 __fastcall(PEVENT_RECORD Event)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140003a30`

## callees

- `0x140004c2c`
- `0x140007ec4`
- `0x14000aa54`
- `0x14001b6cc`
- `0x14001c5d4`
- `0x14001ceb0`
- `0x14001d6a4`

## string_xrefs

- `0x140008269`: `PagesPerSide`
- `0x14000828f`: `FilesOpened`

## pseudocode

```c
unsigned __int64 __fastcall PrintJobCallback(PEVENT_RECORD Event)
{
  struct _THREAD_RECORD *GlobalThreadById; // rax
  struct _THREAD_RECORD *v3; // rsi
  unsigned __int64 result; // rax
  unsigned int v5; // ecx
  unsigned int v6; // eax
  struct _PRINT_JOB_RECORD *PrintJobRecord; // rax
  struct _PRINT_JOB_RECORD *v8; // rdi
  __int64 v9; // r10
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 v12; // rdx
  EVENT_DESCRIPTOR *p_EventDescriptor; // rax
  UCHAR *p_Opcode; // rcx
  UCHAR *v15; // rcx
  unsigned __int64 v16; // rcx
  __int64 v17; // r9
  __int64 i; // r8
  unsigned int v19; // [rsp+50h] [rbp+30h] BYREF
  unsigned int v20; // [rsp+58h] [rbp+38h] BYREF

  v20 = 0;
  v19 = 0;
  GlobalThreadById = FindGlobalThreadById(Event->EventHeader.ThreadId, Event);
  v19 = 4;
  v3 = GlobalThreadById;
  result = GetMofData(Event, L"JobId", (BYTE *)&v20, &v19);
  if ( (_DWORD)result )
    return result;
  v5 = v20;
  if ( v20 )
  {
    if ( v3 )
    {
      v6 = *((_DWORD *)v3 + 55);
      if ( v20 != v6 )
      {
        PrintJobRecord = FindPrintJobRecord(v6);
        UpdateThreadPrintData(PrintJobRecord, Event, v3);
        v5 = v20;
      }
      *((_DWORD *)v3 + 55) = v5;
      v5 = v20;
    }
  }
  else
  {
    if ( !v3 )
      return result;
    v5 = *((_DWORD *)v3 + 55);
    if ( !v5 )
      return result;
    v20 = *((_DWORD *)v3 + 55);
  }
  v8 = FindPrintJobRecord(v5);
  if ( *(_QWORD *)&Event->EventHeader.ProviderId.Data1 == *(_QWORD *)&PrintSpoolerGuid.Data1
    && *(_QWORD *)Event->EventHeader.ProviderId.Data4 == *(_QWORD *)PrintSpoolerGuid.Data4
    && Event->EventHeader.EventDescriptor.Id == 800
    || (result = *(_QWORD *)&Event->EventHeader.ProviderId.Data1, result == *(_QWORD *)&PrintJobGuid.Data1)
    && (result = *(_QWORD *)Event->EventHeader.ProviderId.Data4, result == *(_QWORD *)PrintJobGuid.Data4)
    && Event->EventHeader.EventDescriptor.Opcode == 1 )
  {
    if ( v8 )
      DeletePrintJobRecord(v8, 0);
    result = (unsigned __int64)AddPrintJobRecord(v20);
    v8 = (struct _PRINT_JOB_RECORD *)result;
    if ( !result )
      return result;
    *(_QWORD *)(result + 64) = Event->EventHeader.TimeStamp.QuadPart;
  }
  else if ( !v8 )
  {
    return result;
  }
  UpdateThreadPrintData(v8, Event, v3);
  v9 = *(_QWORD *)&PrintSpoolerGuid.Data1;
  v10 = *(_QWORD *)PrintJobGuid.Data4;
  v11 = *(_QWORD *)&PrintJobGuid.Data1;
  v12 = *(_QWORD *)PrintSpoolerGuid.Data4;
  if ( *(_QWORD *)&Event->EventHeader.ProviderId.Data1 == *(_QWORD *)&PrintSpoolerGuid.Data1
    && *(_QWORD *)Event->EventHeader.ProviderId.Data4 == *(_QWORD *)PrintSpoolerGuid.Data4 )
  {
    p_EventDescriptor = &Event->EventHeader.EventDescriptor;
    if ( Event->EventHeader.EventDescriptor.Id == 802 )
      goto LABEL_46;
  }
  else
  {
    p_EventDescriptor = &Event->EventHeader.EventDescriptor;
  }
  if ( *(_QWORD *)&Event->EventHeader.ProviderId.Data1 == *(_QWORD *)&PrintSpoolerGuid.Data1
    && (*(_QWORD *)Event->EventHeader.ProviderId.Data4 == *(_QWORD *)PrintSpoolerGuid.Data4
     && p_EventDescriptor->Id == 806
     || *(_QWORD *)&Event->EventHeader.ProviderId.Data1 == *(_QWORD *)&PrintSpoolerGuid.Data1
     && *(_QWORD *)Event->EventHeader.ProviderId.Data4 == *(_QWORD *)PrintSpoolerGuid.Data4
     && p_EventDescriptor->Id == 807) )
  {
    goto LABEL_46;
  }
  if ( *(_QWORD *)&Event->EventHeader.ProviderId.Data1 == *(_QWORD *)&PrintJobGuid.Data1
    && *(_QWORD *)Event->EventHeader.ProviderId.Data4 == *(_QWORD *)PrintJobGuid.Data4 )
  {
    p_Opcode = &Event->EventHeader.EventDescriptor.Opcode;
    if ( Event->EventHeader.EventDescriptor.Opcode == 10 )
      goto LABEL_46;
  }
  else
  {
    p_Opcode = &Event->EventHeader.EventDescriptor.Opcode;
  }
  if ( *(_QWORD *)&Event->EventHeader.ProviderId.Data1 == *(_QWORD *)&PrintJobGuid.Data1
    && (*(_QWORD *)Event->EventHeader.ProviderId.Data4 == *(_QWORD *)PrintJobGuid.Data4 && *p_Opcode == 2
     || *(_QWORD *)&Event->EventHeader.ProviderId.Data1 == *(_QWORD *)&PrintJobGuid.Data1
     && (*(_QWORD *)Event->EventHeader.ProviderId.Data4 == *(_QWORD *)PrintJobGuid.Data4 && *p_Opcode == 12
      || *(_QWORD *)&Event->EventHeader.ProviderId.Data1 == *(_QWORD *)&PrintJobGuid.Data1
      && *(_QWORD *)Event->EventHeader.ProviderId.Data4 == *(_QWORD *)PrintJobGuid.Data4
      && *p_Opcode == 13)) )
  {
LABEL_46:
    if ( v3 )
    {
      *((_DWORD *)v3 + 55) = 0;
      v12 = *(_QWORD *)PrintSpoolerGuid.Data4;
      v9 = *(_QWORD *)&PrintSpoolerGuid.Data1;
      v10 = *(_QWORD *)PrintJobGuid.Data4;
      v11 = *(_QWORD *)&PrintJobGuid.Data1;
    }
  }
  if ( *(_QWORD *)&Event->EventHeader.ProviderId.Data1 == v9
    && *(_QWORD *)Event->EventHeader.ProviderId.Data4 == v12
    && p_EventDescriptor->Id == 806 )
  {
    goto LABEL_54;
  }
  if ( *(_QWORD *)&Event->EventHeader.ProviderId.Data1 == v11 && *(_QWORD *)Event->EventHeader.ProviderId.Data4 == v10 )
  {
    v15 = &Event->EventHeader.EventDescriptor.Opcode;
    if ( Event->EventHeader.EventDescriptor.Opcode == 12 )
    {
LABEL_54:
      result = Event->EventHeader.TimeStamp.QuadPart;
      *((_QWORD *)v8 + 12) = result;
      return result;
    }
  }
  else
  {
    v15 = &Event->EventHeader.EventDescriptor.Opcode;
  }
  if ( *(_QWORD *)&Event->EventHeader.ProviderId.Data1 == v9
    && *(_QWORD *)Event->EventHeader.ProviderId.Data4 == v12
    && p_EventDescriptor->Id == 807
    || *(_QWORD *)&Event->EventHeader.ProviderId.Data1 == v11
    && *(_QWORD *)Event->EventHeader.ProviderId.Data4 == v10
    && *v15 == 13 )
  {
    v16 = Event->EventHeader.TimeStamp.QuadPart - *((_QWORD *)v8 + 12);
    result = 0x346DC5D63886594BLL * v16;
    *((_QWORD *)v8 + 12) = 0;
    *((_QWORD *)v8 + 11) += v16 / 0x2710;
  }
  else if ( *(_QWORD *)&Event->EventHeader.ProviderId.Data1 == v9
         && *(_QWORD *)Event->EventHeader.ProviderId.Data4 == v12
         && p_EventDescriptor->Id == 801
         || *(_QWORD *)&Event->EventHeader.ProviderId.Data1 == v11
         && *(_QWORD *)Event->EventHeader.ProviderId.Data4 == v10
         && *v15 == 7 )
  {
    result = Event->EventHeader.TimeStamp.QuadPart;
    *((_QWORD *)v8 + 13) = result;
  }
  else if ( *(_QWORD *)&Event->EventHeader.ProviderId.Data1 == v9
         && *(_QWORD *)Event->EventHeader.ProviderId.Data4 == v12
         && p_EventDescriptor->Id == 802
         || *(_QWORD *)&Event->EventHeader.ProviderId.Data1 == v11
         && *(_QWORD *)Event->EventHeader.ProviderId.Data4 == v10
         && *v15 == 2 )
  {
    *((_QWORD *)v8 + 9) = Event->EventHeader.TimeStamp.QuadPart;
    *((_QWORD *)v8 + 10) += (Event->EventHeader.TimeStamp.QuadPart - *((_QWORD *)v8 + 8)) / 0x2710uLL;
    v19 = 4;
    result = GetMofData(Event, L"JobSize", (BYTE *)v8 + 40, &v19);
    if ( !(_DWORD)result )
    {
      result = GetMofData(Event, L"DataType", (BYTE *)v8 + 36, &v19);
      if ( !(_DWORD)result )
      {
        result = GetMofData(Event, L"Pages", (BYTE *)v8 + 44, &v19);
        if ( !(_DWORD)result )
        {
          result = GetMofData(Event, L"PagesPerSide", (BYTE *)v8 + 48, &v19);
          if ( !(_DWORD)result )
          {
            v19 = 2;
            result = GetMofData(Event, L"FilesOpened", (BYTE *)v8 + 112, &v19);
            if ( !(_DWORD)result )
            {
              v17 = 0;
              *(_QWORD *)((char *)v8 + 20) = 0;
              for ( *(_QWORD *)((char *)v8 + 28) = 0;
                    (unsigned int)v17 < *((_DWORD *)v8 + 32);
                    v17 = (unsigned int)(v17 + 1) )
              {
                for ( i = 0; i != 4; ++i )
                  *((_DWORD *)v8 + i + 5) += *((_DWORD *)v8 + 10 * v17 + i + 38);
              }
              return DeletePrintJobRecord(v8, 1);
            }
          }
        }
      }
    }
  }
  else if ( *(_QWORD *)&Event->EventHeader.ProviderId.Data1 == v9
         && *(_QWORD *)Event->EventHeader.ProviderId.Data4 == v12
         && p_EventDescriptor->Id == 805
         || (result = *(_QWORD *)&Event->EventHeader.ProviderId.Data1, result == 0x485A92A61D32B239LL)
         && (result = *(_QWORD *)Event->EventHeader.ProviderId.Data4, result == 0x3E80FB5936DCD296LL)
         && *v15 == 11 )
  {
    v19 = 4;
    result = GetMofData(Event, L"GdiJobSize", (BYTE *)v8 + 56, &v19);
    if ( !(_DWORD)result )
    {
      result = GetMofData(Event, L"ICMMethod", (BYTE *)v8 + 52, &v19);
      if ( !(_DWORD)result )
      {
        v19 = 2;
        result = GetMofData(Event, L"Color", (BYTE *)v8 + 114, &v19);
        if ( !(_DWORD)result )
        {
          result = GetMofData(Event, L"XRes", (BYTE *)v8 + 116, &v19);
          if ( !(_DWORD)result )
          {
            result = GetMofData(Event, L"YRes", (BYTE *)v8 + 118, &v19);
            if ( !(_DWORD)result )
            {
              result = GetMofData(Event, L"Quality", (BYTE *)v8 + 120, &v19);
              if ( !(_DWORD)result )
              {
                result = GetMofData(Event, L"Copies", (BYTE *)v8 + 122, &v19);
                if ( !(_DWORD)result )
                  return GetMofData(Event, L"TTOption", (BYTE *)v8 + 124, &v19);
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140007ec4  mov     [rsp-28h+arg_10], rbx
0x140007ec9  push    rbp
0x140007eca  push    rsi
0x140007ecb  push    rdi
0x140007ecc  push    r12
0x140007ece  push    r14
0x140007ed0  mov     rbp, rsp
0x140007ed3  sub     rsp, 20h
0x140007ed7  mov     rbx, rcx
0x140007eda  mov     [rbp+arg_8], 0
0x140007ee1  mov     rdx, rcx; struct _EVENT_RECORD *
0x140007ee4  mov     [rbp+arg_0], 0
0x140007eeb  mov     ecx, [rcx+8]; unsigned int
0x140007eee  call    ?FindGlobalThreadById@@YAPEAU_THREAD_RECORD@@KPEAU_EVENT_RECORD@@@Z; FindGlobalThreadById(ulong,_EVENT_RECORD *)
0x140007ef3  lea     r9, [rbp+arg_0]; unsigned int *
0x140007ef7  mov     [rbp+arg_0], 4
0x140007efe  lea     r8, [rbp+arg_8]; void *
0x140007f02  mov     rcx, rbx; Event
0x140007f05  lea     rdx, aJobid; "JobId"
0x140007f0c  mov     rsi, rax
0x140007f0f  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140007f14  test    eax, eax
0x140007f16  jnz     loc_14000842D
0x140007f1c  mov     ecx, [rbp+arg_8]
0x140007f1f  test    ecx, ecx
0x140007f21  jnz     short loc_140007F3F
0x140007f23  test    rsi, rsi
0x140007f26  jz      loc_14000842D
0x140007f2c  mov     ecx, [rsi+0DCh]
0x140007f32  test    ecx, ecx
0x140007f34  jz      loc_14000842D
0x140007f3a  mov     [rbp+arg_8], ecx
0x140007f3d  jmp     short loc_140007F6F
0x140007f3f  test    rsi, rsi
0x140007f42  jz      short loc_140007F6F
0x140007f44  mov     eax, [rsi+0DCh]
0x140007f4a  cmp     ecx, eax
0x140007f4c  jz      short loc_140007F66
0x140007f4e  mov     ecx, eax; unsigned int
0x140007f50  call    ?FindPrintJobRecord@@YAPEAU_PRINT_JOB_RECORD@@K@Z; FindPrintJobRecord(ulong)
0x140007f55  mov     r8, rsi
0x140007f58  mov     rdx, rbx
0x140007f5b  mov     rcx, rax
0x140007f5e  call    UpdateThreadPrintData
0x140007f63  mov     ecx, [rbp+arg_8]
0x140007f66  mov     [rsi+0DCh], ecx
0x140007f6c  mov     ecx, [rbp+arg_8]; unsigned int
0x140007f6f  call    ?FindPrintJobRecord@@YAPEAU_PRINT_JOB_RECORD@@K@Z; FindPrintJobRecord(ulong)
0x140007f74  mov     rdi, rax
0x140007f77  mov     rax, [rbx+18h]
0x140007f7b  cmp     rax, qword ptr cs:?PrintSpoolerGuid@@3U_GUID@@B.Data1; _GUID const PrintSpoolerGuid ...
0x140007f82  jnz     short loc_140007F9C
0x140007f84  mov     rax, [rbx+20h]
0x140007f88  cmp     rax, qword ptr cs:?PrintSpoolerGuid@@3U_GUID@@B.Data4; _GUID const PrintSpoolerGuid ...
0x140007f8f  jnz     short loc_140007F9C
0x140007f91  mov     eax, 320h
0x140007f96  cmp     [rbx+28h], ax
0x140007f9a  jz      short loc_140007FBC
0x140007f9c  mov     rax, [rbx+18h]
0x140007fa0  cmp     rax, qword ptr cs:?PrintJobGuid@@3U_GUID@@B.Data1; _GUID const PrintJobGuid ...
0x140007fa7  jnz     short loc_140007FE9
0x140007fa9  mov     rax, [rbx+20h]
0x140007fad  cmp     rax, qword ptr cs:?PrintJobGuid@@3U_GUID@@B.Data4; _GUID const PrintJobGuid ...
0x140007fb4  jnz     short loc_140007FE9
0x140007fb6  cmp     byte ptr [rbx+2Dh], 1
0x140007fba  jnz     short loc_140007FE9
0x140007fbc  test    rdi, rdi
0x140007fbf  jz      short loc_140007FCB
0x140007fc1  xor     edx, edx; unsigned int
0x140007fc3  mov     rcx, rdi; struct _PRINT_JOB_RECORD *
0x140007fc6  call    ?DeletePrintJobRecord@@YAKPEAU_PRINT_JOB_RECORD@@K@Z; DeletePrintJobRecord(_PRINT_JOB_RECORD *,ulong)
0x140007fcb  mov     ecx, [rbp+arg_8]; unsigned int
0x140007fce  call    ?AddPrintJobRecord@@YAPEAU_PRINT_JOB_RECORD@@K@Z; AddPrintJobRecord(ulong)
0x140007fd3  mov     rdi, rax
0x140007fd6  test    rax, rax
0x140007fd9  jz      loc_14000842D
0x140007fdf  mov     rcx, [rbx+10h]
0x140007fe3  mov     [rax+40h], rcx
0x140007fe7  jmp     short loc_140007FF2
0x140007fe9  test    rdi, rdi
0x140007fec  jz      loc_14000842D
0x140007ff2  mov     r8, rsi
0x140007ff5  mov     rdx, rbx
0x140007ff8  mov     rcx, rdi
0x140007ffb  mov     r14, rdi
0x140007ffe  call    UpdateThreadPrintData
0x140008003  mov     r10, qword ptr cs:?PrintSpoolerGuid@@3U_GUID@@B.Data1; _GUID const PrintSpoolerGuid ...
0x14000800a  mov     r11d, 326h
0x140008010  mov     r9, qword ptr cs:?PrintJobGuid@@3U_GUID@@B.Data4; _GUID const PrintJobGuid ...
0x140008017  mov     r8, qword ptr cs:?PrintJobGuid@@3U_GUID@@B.Data1; _GUID const PrintJobGuid ...
0x14000801e  mov     rdx, qword ptr cs:?PrintSpoolerGuid@@3U_GUID@@B.Data4; _GUID const PrintSpoolerGuid ...
0x140008025  lea     r12d, [r11+1]
0x140008029  lea     ecx, [r11-4]
0x14000802d  cmp     [rbx+18h], r10
0x140008031  jnz     short loc_140008044
0x140008033  cmp     [rbx+20h], rdx
0x140008037  jnz     short loc_140008044
0x140008039  lea     rax, [rbx+28h]
0x14000803d  cmp     [rax], cx
0x140008040  jz      short loc_1400080BA
0x140008042  jmp     short loc_140008048
0x140008044  lea     rax, [rbx+28h]
0x140008048  cmp     [rbx+18h], r10
0x14000804c  jnz     short loc_14000806C
0x14000804e  cmp     [rbx+20h], rdx
0x140008052  jnz     short loc_14000805A
0x140008054  cmp     [rax], r11w
0x140008058  jz      short loc_1400080BA
0x14000805a  cmp     [rbx+18h], r10
0x14000805e  jnz     short loc_14000806C
0x140008060  cmp     [rbx+20h], rdx
0x140008064  jnz     short loc_14000806C
0x140008066  cmp     [rax], r12w
0x14000806a  jz      short loc_1400080BA
0x14000806c  cmp     [rbx+18h], r8
0x140008070  jnz     short loc_140008083
0x140008072  cmp     [rbx+20h], r9
0x140008076  jnz     short loc_140008083
0x140008078  lea     rcx, [rbx+2Dh]
0x14000807c  cmp     byte ptr [rcx], 0Ah
0x14000807f  jnz     short loc_140008087
0x140008081  jmp     short loc_1400080BA
0x140008083  lea     rcx, [rbx+2Dh]
0x140008087  cmp     [rbx+18h], r8
0x14000808b  jnz     short loc_1400080E5
0x14000808d  cmp     [rbx+20h], r9
0x140008091  jnz     short loc_140008098
0x140008093  cmp     byte ptr [rcx], 2
0x140008096  jz      short loc_1400080BA
0x140008098  cmp     [rbx+18h], r8
0x14000809c  jnz     short loc_1400080E5
0x14000809e  cmp     [rbx+20h], r9
0x1400080a2  jnz     short loc_1400080A9
0x1400080a4  cmp     byte ptr [rcx], 0Ch
0x1400080a7  jz      short loc_1400080BA
0x1400080a9  cmp     [rbx+18h], r8
0x1400080ad  jnz     short loc_1400080E5
0x1400080af  cmp     [rbx+20h], r9
0x1400080b3  jnz     short loc_1400080E5
0x1400080b5  cmp     byte ptr [rcx], 0Dh
0x1400080b8  jnz     short loc_1400080E5
0x1400080ba  test    rsi, rsi
0x1400080bd  jz      short loc_1400080E5
0x1400080bf  mov     dword ptr [rsi+0DCh], 0
0x1400080c9  mov     rdx, qword ptr cs:?PrintSpoolerGuid@@3U_GUID@@B.Data4; _GUID const PrintSpoolerGuid ...
0x1400080d0  mov     r10, qword ptr cs:?PrintSpoolerGuid@@3U_GUID@@B.Data1; _GUID const PrintSpoolerGuid ...
0x1400080d7  mov     r9, qword ptr cs:?PrintJobGuid@@3U_GUID@@B.Data4; _GUID const PrintJobGuid ...
0x1400080de  mov     r8, qword ptr cs:?PrintJobGuid@@3U_GUID@@B.Data1; _GUID const PrintJobGuid ...
0x1400080e5  cmp     [rbx+18h], r10
0x1400080e9  jnz     short loc_1400080F7
0x1400080eb  cmp     [rbx+20h], rdx
0x1400080ef  jnz     short loc_1400080F7
0x1400080f1  cmp     [rax], r11w
0x1400080f5  jz      short loc_14000810C
0x1400080f7  cmp     [rbx+18h], r8
0x1400080fb  jnz     short loc_140008119
0x1400080fd  cmp     [rbx+20h], r9
0x140008101  jnz     short loc_140008119
0x140008103  lea     rcx, [rbx+2Dh]
0x140008107  cmp     byte ptr [rcx], 0Ch
0x14000810a  jnz     short loc_14000811D
0x14000810c  mov     rax, [rbx+10h]
0x140008110  mov     [rdi+60h], rax
0x140008114  jmp     loc_14000842D
0x140008119  lea     rcx, [rbx+2Dh]
0x14000811d  cmp     [rbx+18h], r10
0x140008121  jnz     short loc_14000812F
0x140008123  cmp     [rbx+20h], rdx
0x140008127  jnz     short loc_14000812F
0x140008129  cmp     [rax], r12w
0x14000812d  jz      short loc_140008140
0x14000812f  cmp     [rbx+18h], r8
0x140008133  jnz     short loc_14000816A
0x140008135  cmp     [rbx+20h], r9
0x140008139  jnz     short loc_14000816A
0x14000813b  cmp     byte ptr [rcx], 0Dh
0x14000813e  jnz     short loc_14000816A
0x140008140  mov     rcx, [rbx+10h]
0x140008144  mov     rax, 346DC5D63886594Bh
0x14000814e  sub     rcx, [rdi+60h]
0x140008152  mul     rcx
0x140008155  mov     qword ptr [rdi+60h], 0
0x14000815d  shr     rdx, 0Bh
0x140008161  add     [rdi+58h], rdx
0x140008165  jmp     loc_14000842D
0x14000816a  cmp     [rbx+18h], r10
0x14000816e  jnz     short loc_140008182
0x140008170  cmp     [rbx+20h], rdx
0x140008174  jnz     short loc_140008182
0x140008176  mov     r11d, 321h
0x14000817c  cmp     [rax], r11w
0x140008180  jz      short loc_140008193
0x140008182  cmp     [rbx+18h], r8
0x140008186  jnz     short loc_1400081A0
0x140008188  cmp     [rbx+20h], r9
0x14000818c  jnz     short loc_1400081A0
0x14000818e  cmp     byte ptr [rcx], 7
0x140008191  jnz     short loc_1400081A0
0x140008193  mov     rax, [rbx+10h]
0x140008197  mov     [rdi+68h], rax
0x14000819b  jmp     loc_14000842D
0x1400081a0  cmp     [rbx+18h], r10
0x1400081a4  jnz     short loc_1400081B8
0x1400081a6  cmp     [rbx+20h], rdx
0x1400081aa  jnz     short loc_1400081B8
0x1400081ac  mov     r11d, 322h
0x1400081b2  cmp     [rax], r11w
0x1400081b6  jz      short loc_1400081D5
0x1400081b8  cmp     [rbx+18h], r8
0x1400081bc  jnz     loc_1400082FE
0x1400081c2  cmp     [rbx+20h], r9
0x1400081c6  jnz     loc_1400082FE
0x1400081cc  cmp     byte ptr [rcx], 2
0x1400081cf  jnz     loc_1400082FE
0x1400081d5  mov     rax, [rbx+10h]
0x1400081d9  lea     r8, [rdi+28h]; void *
0x1400081dd  mov     [rdi+48h], rax
0x1400081e1  lea     r9, [rbp+arg_0]; unsigned int *
0x1400081e5  mov     rcx, [rbx+10h]
0x1400081e9  mov     rax, 346DC5D63886594Bh
0x1400081f3  sub     rcx, [rdi+40h]
0x1400081f7  mul     rcx
0x1400081fa  mov     rcx, rbx; Event
0x1400081fd  shr     rdx, 0Bh
0x140008201  add     [rdi+50h], rdx
0x140008205  lea     rdx, aJobsize; "JobSize"
0x14000820c  mov     [rbp+arg_0], 4
0x140008213  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140008218  test    eax, eax
0x14000821a  jnz     loc_14000842D
0x140008220  lea     r8, [rdi+24h]; void *
0x140008224  mov     rcx, rbx; Event
0x140008227  lea     r9, [rbp+arg_0]; unsigned int *
0x14000822b  lea     rdx, aDatatype; "DataType"
0x140008232  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140008237  test    eax, eax
0x140008239  jnz     loc_14000842D
0x14000823f  lea     r8, [rdi+2Ch]; void *
0x140008243  mov     rcx, rbx; Event
0x140008246  lea     r9, [rbp+arg_0]; unsigned int *
0x14000824a  lea     rdx, aPages; "Pages"
0x140008251  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140008256  test    eax, eax
0x140008258  jnz     loc_14000842D
0x14000825e  lea     r8, [rdi+30h]; void *
0x140008262  mov     rcx, rbx; Event
0x140008265  lea     r9, [rbp+arg_0]; unsigned int *
0x140008269  lea     rdx, aPagesperside; "PagesPerSide"
0x140008270  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140008275  test    eax, eax
0x140008277  jnz     loc_14000842D
0x14000827d  lea     r8, [rdi+70h]; void *
0x140008281  mov     [rbp+arg_0], 2
0x140008288  lea     r9, [rbp+arg_0]; unsigned int *
0x14000828c  mov     rcx, rbx; Event
0x14000828f  lea     rdx, aFilesopened; "FilesOpened"
0x140008296  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x14000829b  test    eax, eax
0x14000829d  jnz     loc_14000842D
0x1400082a3  xor     r9d, r9d
0x1400082a6  mov     qword ptr [rdi+14h], 0
0x1400082ae  mov     qword ptr [rdi+1Ch], 0
0x1400082b6  cmp     [rdi+80h], r9d
0x1400082bd  jbe     short loc_1400082EC
0x1400082bf  lea     r10, [r9+r9*4]
0x1400082c3  xor     r8d, r8d
0x1400082c6  lea     rax, [r8+r10*2]
0x1400082ca  mov     ecx, [r14+rax*4+98h]
0x1400082d2  add     [rdi+r8*4+14h], ecx
0x1400082d7  inc     r8
0x1400082da  cmp     r8, 4
0x1400082de  jnz     short loc_1400082C6
0x1400082e0  inc     r9d
0x1400082e3  cmp     r9d, [rdi+80h]
0x1400082ea  jb      short loc_1400082BF
0x1400082ec  mov     edx, 1; unsigned int
0x1400082f1  mov     rcx, rdi; struct _PRINT_JOB_RECORD *
0x1400082f4  call    ?DeletePrintJobRecord@@YAKPEAU_PRINT_JOB_RECORD@@K@Z; DeletePrintJobRecord(_PRINT_JOB_RECORD *,ulong)
0x1400082f9  jmp     loc_14000842D
0x1400082fe  cmp     [rbx+18h], r10
0x140008302  jnz     short loc_140008314
0x140008304  cmp     [rbx+20h], rdx
0x140008308  jnz     short loc_140008314
0x14000830a  mov     edx, 325h
0x14000830f  cmp     [rax], dx
0x140008312  jz      short loc_14000833F
0x140008314  mov     rax, [rbx+18h]
0x140008318  cmp     rax, cs:qword_140043B18
0x14000831f  jnz     loc_14000842D
0x140008325  mov     rax, [rbx+20h]
0x140008329  cmp     rax, cs:qword_140043B20
0x140008330  jnz     loc_14000842D
0x140008336  cmp     byte ptr [rcx], 0Bh
0x140008339  jnz     loc_14000842D
0x14000833f  lea     r8, [rdi+38h]; void *
0x140008343  mov     [rbp+arg_0], 4
0x14000834a  lea     r9, [rbp+arg_0]; unsigned int *
0x14000834e  mov     rcx, rbx; Event
0x140008351  lea     rdx, aGdijobsize; "GdiJobSize"
0x140008358  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
  ... truncated ...
```
