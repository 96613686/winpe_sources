# StorProcessNotification

- ea: `0x1401b6950`
- end: `0x1401b6f63`
- name: `StorProcessNotification`
- size: `1555`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1401b6f70`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x14013f698`
- `0x14014b400`
- `0x14014b500`
- `0x1401b6950`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401b699e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401b699e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401b6a79`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401b6cb7`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401b6a79`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401b6cb7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b6f23`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b6f23`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1401b6a0f`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1401b6a0f`
- `ntoskrnl!IofCompleteRequest` at `0x1401b6efb`
- `ntoskrnl!IofCompleteRequest` at `0x1401b6efb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401b6f2f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401b6f2f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b69bc`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b69bc`

## pseudocode

```c
void __fastcall StorProcessNotification(__int64 a1, __int64 a2)
{
  __int64 v2; // r14
  char v3; // r15
  __int64 EventNotificationContext; // rbx
  __int64 v5; // r12
  __int64 *v6; // r13
  PIRP v7; // rax
  PIRP v8; // rsi
  $855E6E2764E11C70E5E2ED271E7BA802 *v9; // rdi
  unsigned int v10; // edx
  bool v11; // zf
  unsigned __int64 v12; // rcx
  _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  int v14; // eax
  int *Information; // rax
  int v16; // ecx
  __int64 *v17; // rdx
  _IO_SECURITY_CONTEXT *SecurityContext; // rdx
  int v19; // eax
  unsigned int v20; // r14d
  unsigned __int8 v21; // r11
  char *v22; // rbx
  char v23; // r12
  _ACCESS_STATE *v24; // r9
  unsigned int v25; // edi
  unsigned __int64 v26; // r10
  __int64 v27; // r8
  int v28; // ecx
  char SecurityQos; // cl
  _IRP *MasterIrp; // rbx
  unsigned int v31; // eax
  unsigned int AccessState; // r14d
  unsigned int v33; // edi
  unsigned __int64 DesiredAccess; // r10
  __int64 v35; // r8
  int v36; // ecx
  char v37; // bl
  char Flags; // r10
  unsigned __int8 *p_SecurityEvaluated; // rax
  char v40; // r8
  unsigned int v41; // eax
  char v42; // al
  __int64 v43; // [rsp+60h] [rbp-9h]
  struct _ERESOURCE *Resource; // [rsp+70h] [rbp+7h]
  __int128 v46; // [rsp+78h] [rbp+Fh] BYREF

  if ( a2 )
  {
    v2 = a2;
    v3 = 0;
    EventNotificationContext = StorGetEventNotificationContext();
    if ( EventNotificationContext )
    {
      KeEnterCriticalRegion();
      Resource = (struct _ERESOURCE *)(EventNotificationContext + 24);
      ExAcquireResourceSharedLite((PERESOURCE)(EventNotificationContext + 24), 1u);
      v5 = EventNotificationContext + 8;
      v6 = *(__int64 **)(EventNotificationContext + 8);
      v43 = EventNotificationContext + 8;
      while ( 1 )
      {
        if ( v6 == (__int64 *)v5 )
        {
          ExReleaseResourceLite(Resource);
          KeLeaveCriticalRegion();
          return;
        }
        if ( (v6[4] & 1) == 0 || (v6[6] & *(_QWORD *)(v2 + 8)) == 0 && (*(_QWORD *)(v2 + 16) & v6[7]) == 0 )
          goto LABEL_112;
        if ( *((__int16 *)v6 + 18) <= 0 )
        {
          _InterlockedAdd((volatile signed __int32 *)v6 + 10, 1u);
          goto LABEL_112;
        }
        v7 = IoCsqRemoveNextIrp((PIO_CSQ)(v6 + 10), 0);
        v8 = v7;
        if ( !v7 )
          goto LABEL_112;
        v9 = &v7->Tail.Overlay.64;
        if ( !*(_DWORD *)(v2 + 32) )
        {
          LOWORD(v10) = 48;
LABEL_56:
          MasterIrp = v7->AssociatedIrp.MasterIrp;
          MasterIrp->Size = v10;
          MasterIrp->Type = 1;
          *(_DWORD *)(&MasterIrp->Size + 1) = 0;
          MasterIrp->MdlAddress = *(_MDL **)(v2 + 8);
          *(_QWORD *)&MasterIrp->Flags = *(_QWORD *)(v2 + 16);
          LODWORD(MasterIrp->ThreadListEntry.Flink) = _InterlockedExchange((volatile __int32 *)v6 + 10, 0);
          HIDWORD(MasterIrp->ThreadListEntry.Flink) = *(_DWORD *)(v2 + 32);
          v31 = *(_DWORD *)(v2 + 32);
          if ( v31 )
            memmove(&MasterIrp->ThreadListEntry.Blink, (const void *)(v2 + 36), v31);
          v11 = StorEtwLoggingEnabled == 0;
          v8->IoStatus.Information = MasterIrp->Size;
          *((_BYTE *)&v8->Tail.CompletionKey + 21) = -84;
          v8->IoStatus.Status = 0;
          if ( v11 )
            goto LABEL_110;
          v46 = 0;
          IoGetActivityIdIrp(v8, &v46);
          CurrentStackLocation = v9->CurrentStackLocation;
          if ( v9->CurrentStackLocation->MajorFunction == 14 )
          {
LABEL_53:
            if ( (byte_140177432 & 8) == 0 )
              goto LABEL_110;
            v17 = EventNonReadWriteRequestComplete;
          }
          else
          {
            v14 = v9->CurrentStackLocation->MajorFunction - 15;
            if ( v9->CurrentStackLocation->MajorFunction == 15 )
            {
              if ( byte_140177431 >= 0 )
                goto LABEL_110;
              SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
              v19 = BYTE2(SecurityContext->SecurityQos);
              if ( (_BYTE)v19 == 40 )
              {
                if ( SecurityContext->FullCreateOptions )
                  goto LABEL_110;
                AccessState = (unsigned int)SecurityContext[2].AccessState;
                if ( !AccessState )
                  goto LABEL_110;
                v21 = 0;
                v22 = 0;
                v23 = 0;
                v24 = 0;
                v33 = 0;
                while ( 1 )
                {
                  v12 = *((unsigned int *)&SecurityContext[5].SecurityQos + v33);
                  if ( (unsigned int)v12 >= 0x80 )
                  {
                    DesiredAccess = SecurityContext->DesiredAccess;
                    if ( (unsigned int)v12 < (unsigned int)DesiredAccess )
                    {
                      v35 = (unsigned int)v12;
                      v36 = *(_DWORD *)((char *)&SecurityContext->SecurityQos + v12) - 64;
                      if ( v36 )
                      {
                        LODWORD(v12) = v36 - 1;
                        if ( (_DWORD)v12 )
                        {
                          if ( (_DWORD)v12 == 1 )
                          {
                            LODWORD(v12) = v35 + 40;
                            if ( v35 + 40 <= DesiredAccess )
                            {
                              v3 = 0;
                              if ( *(_DWORD *)((char *)&SecurityContext->AccessState + v35 + 4) )
                                v22 = (char *)&SecurityContext[1].AccessState + v35;
                              v24 = *(_ACCESS_STATE **)((char *)&SecurityContext[1].SecurityQos + v35);
LABEL_75:
                              v23 = *((_BYTE *)&SecurityContext->AccessState + v35);
                              v21 = *((_BYTE *)&SecurityContext->AccessState + v35 + 1);
                              goto LABEL_48;
                            }
                          }
                        }
                        else
                        {
                          LODWORD(v12) = v35 + 56;
                          if ( v35 + 56 <= DesiredAccess )
                          {
                            v3 = 1;
                            if ( *((_BYTE *)&SecurityContext->AccessState + v35 + 2) )
                              v22 = (char *)&SecurityContext[1] + v35;
                            v23 = *((_BYTE *)&SecurityContext->AccessState + v35);
                            v24 = *(_ACCESS_STATE **)((char *)&SecurityContext->DesiredAccess + v35);
                            v21 = *((_BYTE *)&SecurityContext->AccessState + v35 + 1);
                          }
                        }
                      }
                      else
                      {
                        LODWORD(v12) = v35 + 40;
                        if ( v35 + 40 <= DesiredAccess )
                        {
                          v3 = 0;
                          if ( *((_BYTE *)&SecurityContext->AccessState + v35 + 2) )
                            v22 = (char *)&SecurityContext[1] + v35;
                          v24 = *(_ACCESS_STATE **)((char *)&SecurityContext->DesiredAccess + v35);
                          goto LABEL_75;
                        }
                      }
                      if ( v3 )
                        goto LABEL_47;
                    }
                  }
                  if ( ++v33 >= AccessState )
                  {
LABEL_47:
                    v3 = 0;
                    goto LABEL_48;
                  }
                }
              }
LABEL_87:
              v23 = BYTE4(SecurityContext->SecurityQos);
              v21 = BYTE3(SecurityContext->AccessState);
              v24 = SecurityContext[1].AccessState;
              SecurityQos = (char)SecurityContext[3].SecurityQos;
              if ( v19 )
                goto LABEL_109;
LABEL_88:
              LOBYTE(v12) = SecurityQos - 8;
              if ( (v12 & 0x5D) != 0 )
                goto LABEL_108;
              v37 = BYTE3(SecurityContext->SecurityQos);
              if ( v37 == 1 || !v24 || !v21 )
                goto LABEL_106;
              LOBYTE(SecurityContext) = 0;
              v12 = (unsigned __int64)v24 + v21;
              Flags = 0;
              p_SecurityEvaluated = &v24->SecurityEvaluated;
              v40 = 0;
              if ( (unsigned __int8)((v24->OperationID.LowPart & 0x7F) - 114) <= 1u )
              {
                if ( (unsigned __int64)p_SecurityEvaluated <= v12 )
                {
                  Flags = BYTE2(v24->OperationID.LowPart);
                  v40 = BYTE1(v24->OperationID.LowPart) & 0xF;
                  LOBYTE(SecurityContext) = HIBYTE(v24->OperationID.LowPart);
                  goto LABEL_103;
                }
              }
              else if ( (unsigned __int64)p_SecurityEvaluated <= v12 )
              {
                SecurityContext = (_IO_SECURITY_CONTEXT *)((char *)&v24->Flags + 1);
                v40 = BYTE2(v24->OperationID.LowPart) & 0xF;
                v41 = v21;
                if ( (unsigned int)HIBYTE(v24->OperationID.HighPart) + 8 <= v21 )
                  v41 = HIBYTE(v24->OperationID.HighPart) + 8;
                v12 = (unsigned __int64)v24 + v41;
                if ( (unsigned __int64)SecurityContext <= v12 )
                  Flags = v24->Flags;
                if ( (unsigned __int64)&v24->Flags + 2 > v12 )
                  LOBYTE(SecurityContext) = 0;
                else
                  LOBYTE(SecurityContext) = SecurityContext->SecurityQos;
LABEL_103:
                v42 = 1;
LABEL_105:
                if ( !v42 )
                {
LABEL_106:
                  v40 = 0;
                  Flags = 0;
                  LOBYTE(SecurityContext) = 0;
                }
                McTemplateK0pduuuuup_EtwWriteTransfer(
                  v12,
                  (_DWORD)SecurityContext,
                  (unsigned int)&v46,
                  (_DWORD)v8,
                  v8->IoStatus.Status,
                  v37,
                  v23,
                  v40,
                  Flags,
                  (char)SecurityContext,
                  (char)v8);
LABEL_108:
                v5 = v43;
                goto LABEL_110;
              }
              v42 = 0;
              goto LABEL_105;
            }
LABEL_14:
            if ( v14 != 12 )
              goto LABEL_110;
            if ( CurrentStackLocation->MinorFunction == 7 && !CurrentStackLocation->Parameters.Read.Length )
            {
              if ( (byte_140177432 & 0x40) != 0 )
              {
                Information = (int *)v8->IoStatus.Information;
                if ( Information )
                  v16 = *Information;
                else
                  v16 = 0;
                McTemplateK0pqd_EtwWriteTransfer(
                  v16,
                  (_DWORD)CurrentStackLocation,
                  (unsigned int)&v46,
                  (_DWORD)v8,
                  v16,
                  v8->IoStatus.Status);
              }
              goto LABEL_110;
            }
            if ( (byte_140177432 & 0x20) == 0 )
              goto LABEL_110;
            v17 = EventPnpRequestComplete;
          }
          McTemplateK0pd_EtwWriteTransfer(v12, v17, &v46, v8, v8->IoStatus.Status);
          goto LABEL_110;
        }
        v10 = (unsigned __int16)(*(_WORD *)(v2 + 32) + 40);
        if ( v9->CurrentStackLocation->Parameters.Read.Length >= v10 )
          goto LABEL_56;
        v11 = StorEtwLoggingEnabled == 0;
        *((_BYTE *)&v7->Tail.CompletionKey + 21) = -84;
        v7->IoStatus.Status = -1073741789;
        if ( v11 )
          goto LABEL_110;
        v46 = 0;
        IoGetActivityIdIrp(v7, &v46);
        CurrentStackLocation = v9->CurrentStackLocation;
        if ( v9->CurrentStackLocation->MajorFunction == 14 )
          goto LABEL_53;
        v14 = v9->CurrentStackLocation->MajorFunction - 15;
        if ( v9->CurrentStackLocation->MajorFunction != 15 )
          goto LABEL_14;
        if ( byte_140177431 >= 0 )
          goto LABEL_110;
        SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
        v19 = BYTE2(SecurityContext->SecurityQos);
        if ( (_BYTE)v19 != 40 )
          goto LABEL_87;
        if ( SecurityContext->FullCreateOptions )
          goto LABEL_110;
        v20 = (unsigned int)SecurityContext[2].AccessState;
        if ( !v20 )
          goto LABEL_110;
        v21 = 0;
        v22 = 0;
        v23 = 0;
        v24 = 0;
        v25 = 0;
        while ( 1 )
        {
          v12 = *((unsigned int *)&SecurityContext[5].SecurityQos + v25);
          if ( (unsigned int)v12 >= 0x80 )
          {
            v26 = SecurityContext->DesiredAccess;
            if ( (unsigned int)v12 < (unsigned int)v26 )
              break;
          }
LABEL_46:
          if ( ++v25 >= v20 )
            goto LABEL_47;
        }
        v27 = (unsigned int)v12;
        v28 = *(_DWORD *)((char *)&SecurityContext->SecurityQos + v12) - 64;
        if ( v28 )
          break;
        LODWORD(v12) = v27 + 40;
        if ( v27 + 40 > v26 )
          goto LABEL_45;
        v3 = 0;
        if ( *((_BYTE *)&SecurityContext->AccessState + v27 + 2) )
          v22 = (char *)&SecurityContext[1] + v27;
        v24 = *(_ACCESS_STATE **)((char *)&SecurityContext->DesiredAccess + v27);
LABEL_39:
        v23 = *((_BYTE *)&SecurityContext->AccessState + v27);
        v21 = *((_BYTE *)&SecurityContext->AccessState + v27 + 1);
LABEL_48:
        if ( v22 )
        {
          SecurityQos = *v22;
          goto LABEL_88;
        }
LABEL_109:
        v5 = v43;
LABEL_110:
        IofCompleteRequest(v8, 0);
        v2 = a2;
LABEL_112:
        v6 = (__int64 *)*v6;
      }
      LODWORD(v12) = v28 - 1;
      if ( (_DWORD)v12 )
      {
        if ( (_DWORD)v12 == 1 )
        {
          LODWORD(v12) = v27 + 40;
          if ( v27 + 40 <= v26 )
          {
            v3 = 0;
            if ( *(_DWORD *)((char *)&SecurityContext->AccessState + v27 + 4) )
              v22 = (char *)&SecurityContext[1].AccessState + v27;
            v24 = *(_ACCESS_STATE **)((char *)&SecurityContext[1].SecurityQos + v27);
            goto LABEL_39;
          }
        }
      }
      else
      {
        LODWORD(v12) = v27 + 56;
        if ( v27 + 56 <= v26 )
        {
          v3 = 1;
          if ( *((_BYTE *)&SecurityContext->AccessState + v27 + 2) )
            v22 = (char *)&SecurityContext[1] + v27;
          v23 = *((_BYTE *)&SecurityContext->AccessState + v27);
          v24 = *(_ACCESS_STATE **)((char *)&SecurityContext->DesiredAccess + v27);
          v21 = *((_BYTE *)&SecurityContext->AccessState + v27 + 1);
        }
      }
LABEL_45:
      if ( v3 )
        goto LABEL_47;
      goto LABEL_46;
    }
  }
}

```

## disassembly

```asm
0x1401b6950  test    rdx, rdx
0x1401b6953  jz      locret_1401B6F61
0x1401b6959  mov     [rsp-8+arg_10], rbx
0x1401b695e  push    rbp
0x1401b695f  push    rsi
0x1401b6960  push    rdi
0x1401b6961  push    r12
0x1401b6963  push    r13
0x1401b6965  push    r14
0x1401b6967  push    r15
0x1401b6969  lea     rbp, [rsp-27h]
0x1401b696e  sub     rsp, 90h
0x1401b6975  mov     rax, cs:__security_cookie
0x1401b697c  xor     rax, rsp
0x1401b697f  mov     [rbp+57h+var_38], rax
0x1401b6983  mov     r14, rdx
0x1401b6986  mov     [rbp+57h+var_58], rdx
0x1401b698a  xor     r15d, r15d
0x1401b698d  call    StorGetEventNotificationContext
0x1401b6992  mov     rbx, rax
0x1401b6995  test    rax, rax
0x1401b6998  jz      loc_1401B6F3B
0x1401b699e  call    cs:__imp_KeEnterCriticalRegion
0x1401b69a5  nop     dword ptr [rax+rax+00h]
0x1401b69aa  lea     rax, [rbx+18h]
0x1401b69ae  lea     edi, [r15+1]
0x1401b69b2  mov     [rbp+57h+Resource], rax
0x1401b69b6  mov     rcx, rax; Resource
0x1401b69b9  mov     dl, dil; Wait
0x1401b69bc  call    cs:__imp_ExAcquireResourceSharedLite
0x1401b69c3  nop     dword ptr [rax+rax+00h]
0x1401b69c8  lea     r12, [rbx+8]
0x1401b69cc  mov     r13, [r12]
0x1401b69d0  mov     [rbp+57h+var_60], r12
0x1401b69d4  jmp     loc_1401B6F16
0x1401b69d9  test    [r13+20h], dil
0x1401b69dd  jz      loc_1401B6F12
0x1401b69e3  mov     rax, [r13+30h]
0x1401b69e7  test    [r14+8], rax
0x1401b69eb  jnz     short loc_1401B69FB
0x1401b69ed  mov     rax, [r14+10h]
0x1401b69f1  test    [r13+38h], rax
0x1401b69f5  jz      loc_1401B6F12
0x1401b69fb  movzx   eax, word ptr [r13+24h]
0x1401b6a00  test    ax, ax
0x1401b6a03  jle     loc_1401B6F0D
0x1401b6a09  lea     rcx, [r13+50h]; Csq
0x1401b6a0d  xor     edx, edx; PeekContext
0x1401b6a0f  call    cs:__imp_IoCsqRemoveNextIrp
0x1401b6a16  nop     dword ptr [rax+rax+00h]
0x1401b6a1b  mov     rsi, rax
0x1401b6a1e  test    rax, rax
0x1401b6a21  jz      loc_1401B6F12
0x1401b6a27  lea     rdi, [rax+0B8h]
0x1401b6a2e  cmp     [r14+20h], r15d
0x1401b6a32  jbe     loc_1401B6C3A
0x1401b6a38  movzx   ecx, word ptr [r14+20h]
0x1401b6a3d  add     cx, 28h ; '('
0x1401b6a41  movzx   edx, cx
0x1401b6a44  mov     rcx, [rdi]
0x1401b6a47  cmp     [rcx+8], edx
0x1401b6a4a  jnb     loc_1401B6C3F
0x1401b6a50  cmp     cs:StorEtwLoggingEnabled, r15b
0x1401b6a57  mov     byte ptr [rax+8Dh], 0ACh
0x1401b6a5e  mov     dword ptr [rax+30h], 0C0000023h
0x1401b6a65  jz      loc_1401B6EF1
0x1401b6a6b  xorps   xmm0, xmm0
0x1401b6a6e  lea     rdx, [rbp+57h+var_48]
0x1401b6a72  mov     rcx, rax
0x1401b6a75  movups  [rbp+57h+var_48], xmm0
0x1401b6a79  call    cs:__imp_IoGetActivityIdIrp
0x1401b6a80  nop     dword ptr [rax+rax+00h]
0x1401b6a85  mov     rdx, [rdi]
0x1401b6a88  movzx   eax, byte ptr [rdx]
0x1401b6a8b  sub     eax, 0Eh
0x1401b6a8e  jz      loc_1401B6C21
0x1401b6a94  sub     eax, 1
0x1401b6a97  jz      short loc_1401B6B13
0x1401b6a99  cmp     eax, 0Ch
0x1401b6a9c  jnz     loc_1401B6EF1
0x1401b6aa2  cmp     byte ptr [rdx+1], 7
0x1401b6aa6  jnz     short loc_1401B6AE7
0x1401b6aa8  cmp     [rdx+8], r15d
0x1401b6aac  jnz     short loc_1401B6AE7
0x1401b6aae  test    cs:byte_140177432, 40h
0x1401b6ab5  jz      loc_1401B6EF1
0x1401b6abb  mov     rax, [rsi+38h]
0x1401b6abf  test    rax, rax
0x1401b6ac2  jz      short loc_1401B6AC8
0x1401b6ac4  mov     ecx, [rax]
0x1401b6ac6  jmp     short loc_1401B6ACB
0x1401b6ac8  mov     ecx, r15d
0x1401b6acb  mov     eax, [rsi+30h]
0x1401b6ace  lea     r8, [rbp+57h+var_48]
0x1401b6ad2  mov     [rsp+0C0h+var_98], eax
0x1401b6ad6  mov     r9, rsi
0x1401b6ad9  mov     [rsp+0C0h+var_A0], ecx
0x1401b6add  call    McTemplateK0pqd_EtwWriteTransfer
0x1401b6ae2  jmp     loc_1401B6EF1
0x1401b6ae7  test    cs:byte_140177432, 20h
0x1401b6aee  jz      loc_1401B6EF1
0x1401b6af4  lea     rdx, EventPnpRequestComplete
0x1401b6afb  mov     eax, [rsi+30h]
0x1401b6afe  lea     r8, [rbp+57h+var_48]
0x1401b6b02  mov     r9, rsi
0x1401b6b05  mov     [rsp+0C0h+var_A0], eax
0x1401b6b09  call    McTemplateK0pd_EtwWriteTransfer
0x1401b6b0e  jmp     loc_1401B6EF1
0x1401b6b13  cmp     cs:byte_140177431, r15b
0x1401b6b1a  jge     loc_1401B6EF1
0x1401b6b20  mov     rdx, [rdx+8]
0x1401b6b24  movzx   eax, byte ptr [rdx+2]
0x1401b6b28  cmp     al, 28h ; '('
0x1401b6b2a  jnz     loc_1401B6DE6
0x1401b6b30  cmp     [rdx+14h], r15d
0x1401b6b34  jnz     loc_1401B6EF1
0x1401b6b3a  mov     r14d, [rdx+38h]
0x1401b6b3e  test    r14d, r14d
0x1401b6b41  jz      loc_1401B6EF1
0x1401b6b47  mov     r11b, r15b
0x1401b6b4a  mov     rbx, r15
0x1401b6b4d  mov     r12b, r15b
0x1401b6b50  mov     r9, r15
0x1401b6b53  mov     edi, r15d
0x1401b6b56  mov     eax, edi
0x1401b6b58  mov     ecx, [rdx+rax*4+78h]
0x1401b6b5c  cmp     ecx, 80h
0x1401b6b62  jb      loc_1401B6BEB
0x1401b6b68  mov     r10d, [rdx+10h]
0x1401b6b6c  cmp     ecx, r10d
0x1401b6b6f  jnb     short loc_1401B6BEB
0x1401b6b71  mov     r8d, ecx
0x1401b6b74  mov     ecx, [rcx+rdx]
0x1401b6b77  sub     ecx, 40h ; '@'
0x1401b6b7a  jz      short loc_1401B6BDD
0x1401b6b7c  sub     ecx, 1
0x1401b6b7f  jz      short loc_1401B6BB1
0x1401b6b81  cmp     ecx, 1
0x1401b6b84  jnz     short loc_1401B6BE6
0x1401b6b86  lea     rcx, [r8+28h]
0x1401b6b8a  cmp     rcx, r10
0x1401b6b8d  ja      short loc_1401B6BE6
0x1401b6b8f  xor     r15d, r15d
0x1401b6b92  cmp     [r8+rdx+0Ch], r15d
0x1401b6b97  jbe     short loc_1401B6BA0
0x1401b6b99  lea     rbx, [r8+20h]
0x1401b6b9d  add     rbx, rdx
0x1401b6ba0  mov     r9, [r8+rdx+18h]
0x1401b6ba5  mov     r12b, [r8+rdx+8]
0x1401b6baa  mov     r11b, [r8+rdx+9]
0x1401b6baf  jmp     short loc_1401B6BF9
0x1401b6bb1  lea     rcx, [r8+38h]
0x1401b6bb5  cmp     rcx, r10
0x1401b6bb8  ja      short loc_1401B6BE6
0x1401b6bba  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401b6bc0  mov     r15b, 1
0x1401b6bc3  jbe     short loc_1401B6BCC
0x1401b6bc5  lea     rbx, [r8+18h]
0x1401b6bc9  add     rbx, rdx
0x1401b6bcc  mov     r12b, [r8+rdx+8]
0x1401b6bd1  mov     r9, [r8+rdx+10h]
0x1401b6bd6  mov     r11b, [r8+rdx+9]
0x1401b6bdb  jmp     short loc_1401B6BE6
0x1401b6bdd  lea     rcx, [r8+28h]
0x1401b6be1  cmp     rcx, r10
0x1401b6be4  jbe     short loc_1401B6C09
0x1401b6be6  test    r15b, r15b
0x1401b6be9  jnz     short loc_1401B6BF6
0x1401b6beb  inc     edi
0x1401b6bed  cmp     edi, r14d
0x1401b6bf0  jb      loc_1401B6B56
0x1401b6bf6  xor     r15d, r15d
0x1401b6bf9  test    rbx, rbx
0x1401b6bfc  jz      loc_1401B6EED
0x1401b6c02  mov     cl, [rbx]
0x1401b6c04  jmp     loc_1401B6DFD
0x1401b6c09  xor     r15d, r15d
0x1401b6c0c  cmp     [r8+rdx+0Ah], r15b
0x1401b6c11  jbe     short loc_1401B6C1A
0x1401b6c13  lea     rbx, [r8+18h]
0x1401b6c17  add     rbx, rdx
0x1401b6c1a  mov     r9, [r8+rdx+10h]
0x1401b6c1f  jmp     short loc_1401B6BA5
0x1401b6c21  test    cs:byte_140177432, 8
0x1401b6c28  jz      loc_1401B6EF1
0x1401b6c2e  lea     rdx, EventNonReadWriteRequestComplete
0x1401b6c35  jmp     loc_1401B6AFB
0x1401b6c3a  mov     edx, 30h ; '0'
0x1401b6c3f  mov     rbx, [rax+18h]
0x1401b6c43  mov     [rbx+2], dx
0x1401b6c47  mov     word ptr [rbx], 1
0x1401b6c4c  mov     [rbx+4], r15d
0x1401b6c50  mov     rax, [r14+8]
0x1401b6c54  mov     [rbx+8], rax
0x1401b6c58  mov     rax, [r14+10h]
0x1401b6c5c  mov     [rbx+10h], rax
0x1401b6c60  mov     eax, r15d
0x1401b6c63  xchg    eax, [r13+28h]
0x1401b6c67  mov     [rbx+20h], eax
0x1401b6c6a  mov     eax, [r14+20h]
0x1401b6c6e  mov     [rbx+24h], eax
0x1401b6c71  mov     eax, [r14+20h]
0x1401b6c75  test    eax, eax
0x1401b6c77  jz      short loc_1401B6C89
0x1401b6c79  mov     r8d, eax; Size
0x1401b6c7c  lea     rdx, [r14+24h]; Src
0x1401b6c80  lea     rcx, [rbx+28h]; void *
0x1401b6c84  call    memmove
0x1401b6c89  cmp     cs:StorEtwLoggingEnabled, r15b
0x1401b6c90  movzx   eax, word ptr [rbx+2]
0x1401b6c94  mov     [rsi+38h], rax
0x1401b6c98  mov     byte ptr [rsi+8Dh], 0ACh
0x1401b6c9f  mov     [rsi+30h], r15d
0x1401b6ca3  jz      loc_1401B6EF1
0x1401b6ca9  xorps   xmm0, xmm0
0x1401b6cac  lea     rdx, [rbp+57h+var_48]
0x1401b6cb0  mov     rcx, rsi
0x1401b6cb3  movups  [rbp+57h+var_48], xmm0
0x1401b6cb7  call    cs:__imp_IoGetActivityIdIrp
0x1401b6cbe  nop     dword ptr [rax+rax+00h]
0x1401b6cc3  mov     rdx, [rdi]
0x1401b6cc6  movzx   eax, byte ptr [rdx]
0x1401b6cc9  sub     eax, 0Eh
0x1401b6ccc  jz      loc_1401B6C21
0x1401b6cd2  sub     eax, 1
0x1401b6cd5  jnz     loc_1401B6A99
0x1401b6cdb  cmp     cs:byte_140177431, r15b
0x1401b6ce2  jge     loc_1401B6EF1
0x1401b6ce8  mov     rdx, [rdx+8]
0x1401b6cec  movzx   eax, byte ptr [rdx+2]
0x1401b6cf0  cmp     al, 28h ; '('
0x1401b6cf2  jnz     loc_1401B6DE6
0x1401b6cf8  cmp     [rdx+14h], r15d
0x1401b6cfc  jnz     loc_1401B6EF1
0x1401b6d02  mov     r14d, [rdx+38h]
0x1401b6d06  test    r14d, r14d
0x1401b6d09  jz      loc_1401B6EF1
0x1401b6d0f  mov     r11b, r15b
0x1401b6d12  mov     rbx, r15
0x1401b6d15  mov     r12b, r15b
0x1401b6d18  mov     r9, r15
0x1401b6d1b  mov     edi, r15d
0x1401b6d1e  mov     eax, edi
0x1401b6d20  mov     ecx, [rdx+rax*4+78h]
0x1401b6d24  cmp     ecx, 80h
0x1401b6d2a  jb      loc_1401B6DBE
0x1401b6d30  mov     r10d, [rdx+10h]
0x1401b6d34  cmp     ecx, r10d
0x1401b6d37  jnb     loc_1401B6DBE
0x1401b6d3d  mov     r8d, ecx
0x1401b6d40  mov     ecx, [rdx+rcx]
0x1401b6d43  sub     ecx, 40h ; '@'
0x1401b6d46  jz      short loc_1401B6DAC
0x1401b6d48  sub     ecx, 1
0x1401b6d4b  jz      short loc_1401B6D80
0x1401b6d4d  cmp     ecx, 1
0x1401b6d50  jnz     short loc_1401B6DB5
0x1401b6d52  lea     rcx, [r8+28h]
0x1401b6d56  cmp     rcx, r10
0x1401b6d59  ja      short loc_1401B6DB5
0x1401b6d5b  xor     r15d, r15d
0x1401b6d5e  cmp     [rdx+r8+0Ch], r15d
0x1401b6d63  jbe     short loc_1401B6D6C
0x1401b6d65  lea     rbx, [r8+20h]
0x1401b6d69  add     rbx, rdx
0x1401b6d6c  mov     r9, [rdx+r8+18h]
0x1401b6d71  mov     r12b, [rdx+r8+8]
0x1401b6d76  mov     r11b, [rdx+r8+9]
0x1401b6d7b  jmp     loc_1401B6BF9
0x1401b6d80  lea     rcx, [r8+38h]
0x1401b6d84  cmp     rcx, r10
0x1401b6d87  ja      short loc_1401B6DB5
0x1401b6d89  cmp     byte ptr [rdx+r8+0Ah], 0
0x1401b6d8f  mov     r15b, 1
0x1401b6d92  jbe     short loc_1401B6D9B
0x1401b6d94  lea     rbx, [r8+18h]
0x1401b6d98  add     rbx, rdx
0x1401b6d9b  mov     r12b, [rdx+r8+8]
0x1401b6da0  mov     r9, [rdx+r8+10h]
0x1401b6da5  mov     r11b, [rdx+r8+9]
0x1401b6daa  jmp     short loc_1401B6DB5
0x1401b6dac  lea     rcx, [r8+28h]
0x1401b6db0  cmp     rcx, r10
0x1401b6db3  jbe     short loc_1401B6DCE
0x1401b6db5  test    r15b, r15b
0x1401b6db8  jnz     loc_1401B6BF6
0x1401b6dbe  inc     edi
0x1401b6dc0  cmp     edi, r14d
0x1401b6dc3  jb      loc_1401B6D1E
0x1401b6dc9  jmp     loc_1401B6BF6
0x1401b6dce  xor     r15d, r15d
0x1401b6dd1  cmp     [rdx+r8+0Ah], r15b
0x1401b6dd6  jbe     short loc_1401B6DDF
0x1401b6dd8  lea     rbx, [r8+18h]
0x1401b6ddc  add     rbx, rdx
0x1401b6ddf  mov     r9, [rdx+r8+10h]
0x1401b6de4  jmp     short loc_1401B6D71
0x1401b6de6  mov     r12b, [rdx+4]
0x1401b6dea  mov     r11b, [rdx+0Bh]
0x1401b6dee  mov     r9, [rdx+20h]
  ... truncated ...
```
