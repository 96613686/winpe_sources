# WcPreCreate

- ea: `0x140024380`
- end: `0x14002486d`
- name: `WcPreCreate`
- size: `1261`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, _QWORD *, PFLT_FILE_NAME_INFORMATION **)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callees

- `0x140001580`
- `0x1400020c4`
- `0x140024380`
- `0x140030438`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400245e0`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400245fb`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400245e0`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400245fb`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14002447e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400244f9`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140024643`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14002447e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400244f9`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140024643`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400245c5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400245c5`
- `FLTMGR!FltGetFileNameInformation` at `0x140024461`
- `FLTMGR!FltGetFileNameInformation` at `0x14002475a`
- `FLTMGR!FltGetFileNameInformation` at `0x140024461`
- `FLTMGR!FltGetFileNameInformation` at `0x14002475a`
- `FLTMGR!FltAddOpenReparseEntry` at `0x1400244cc`
- `FLTMGR!FltAddOpenReparseEntry` at `0x140024541`
- `FLTMGR!FltAddOpenReparseEntry` at `0x140024688`
- `FLTMGR!FltAddOpenReparseEntry` at `0x1400244cc`
- `FLTMGR!FltAddOpenReparseEntry` at `0x140024541`
- `FLTMGR!FltAddOpenReparseEntry` at `0x140024688`

## string_xrefs

- `0x1400246cb`: `onecore\base\fs\wci\wcifs\create.c`

## pseudocode

```c
__int64 __fastcall WcPreCreate(PFLT_CALLBACK_DATA CallbackData, _QWORD *a2, PFLT_FILE_NAME_INFORMATION **a3)
{
  struct _FLT_FILE_NAME_INFORMATION *v3; // r15
  __int64 v5; // rdx
  unsigned int v8; // ebx
  __int64 v9; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v10; // rbp
  PFLT_FILE_NAME_INFORMATION *v11; // r15
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  UCHAR OperationFlags; // al
  int v15; // edx
  int v16; // edi
  char *v17; // rax
  struct _FLT_FILE_NAME_INFORMATION *v18; // rbx
  char *v19; // rax
  unsigned int v20; // r12d
  char *v21; // rax
  int v22; // r9d
  char v23; // [rsp+30h] [rbp-58h]
  char v24; // [rsp+38h] [rbp-50h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation[3]; // [rsp+40h] [rbp-48h] BYREF
  int v26; // [rsp+98h] [rbp+10h] BYREF
  unsigned int v27; // [rsp+A8h] [rbp+20h] BYREF

  FileNameInformation[0] = 0;
  v5 = a2[4];
  v27 = 268369920;
  v8 = 1;
  if ( (*(_DWORD *)(v5 + 80) & 0x400000) != 0 )
    return 1;
  v9 = a2[3];
  FileNameInformation[2] = v3;
  v10 = 0;
  v11 = 0;
  if ( (unsigned __int8)WcUnionsExistForInstance(v9, v5, &v26, &v27) )
  {
    if ( a2[5] )
    {
      v16 = WcPreTransaction(CallbackData);
      if ( v16 >= 0 )
        goto LABEL_3;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v24 = v16;
        v22 = 51;
        v23 = -100;
        goto LABEL_33;
      }
    }
    else
    {
      Iopb = CallbackData->Iopb;
      if ( (Iopb->Parameters.Create.Options & 0x2000) != 0
        || ((OperationFlags = Iopb->OperationFlags, (OperationFlags & 4) != 0)
          ? (Iopb->OperationFlags = OperationFlags & 0xFB,
             v16 = FltGetFileNameInformation(CallbackData, 0x302u, FileNameInformation),
             CallbackData->Iopb->OperationFlags |= 4u)
          : (v16 = FltGetFileNameInformation(CallbackData, 0x102u, FileNameInformation)),
            v16 >= 0) )
      {
        v17 = (char *)ExAllocateFromPagedLookasideList(&stru_14000E400);
        v11 = (PFLT_FILE_NAME_INFORMATION *)v17;
        if ( v17 )
        {
          *((_QWORD *)v17 + 1) = v17;
          *(_QWORD *)v17 = v17;
          *(_OWORD *)(v17 + 24) = 0;
          *((_DWORD *)v17 + 4) = 268369920;
          *((_DWORD *)v17 + 5) = -2147483644;
          *((_DWORD *)v17 + 10) = 48;
          v16 = FltAddOpenReparseEntry(Globals, CallbackData, v17);
          if ( v16 < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v24 = v16;
              v22 = 54;
              v23 = -34;
              goto LABEL_33;
            }
          }
          else
          {
            v18 = 0;
            if ( (CallbackData->Iopb->Parameters.Create.Options & 0x200000) == 0 )
              goto LABEL_22;
            v19 = (char *)ExAllocateFromPagedLookasideList(&stru_14000E380);
            v10 = (struct _FLT_FILE_NAME_INFORMATION *)v19;
            if ( !v19 )
            {
              v16 = -1073741670;
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v24 = -102;
                v22 = 55;
                v23 = -18;
                goto LABEL_33;
              }
              goto LABEL_25;
            }
            *((_QWORD *)v19 + 1) = v19;
            *(_QWORD *)v19 = v19;
            *(_OWORD *)(v19 + 24) = 0;
            *((_DWORD *)v19 + 4) = -1610612705;
            *((_DWORD *)v19 + 10) = 48;
            *((_DWORD *)v19 + 5) = -2147483522;
            v16 = FltAddOpenReparseEntry(Globals, CallbackData, v19);
            if ( v16 < 0 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v24 = v16;
                v22 = 56;
                v23 = 0;
                goto LABEL_33;
              }
              goto LABEL_25;
            }
            v20 = v27;
            if ( (v27 & 0xFFF0000) != 0
              || v27 <= 2
              || (v27 & 0xC0000000) == 0x40000000
              || (v27 & 0x30000000) == 0x30000000 )
            {
              goto LABEL_22;
            }
            v21 = (char *)ExAllocateFromPagedLookasideList(&stru_14000E380);
            v18 = (struct _FLT_FILE_NAME_INFORMATION *)v21;
            if ( !v21 )
            {
              v16 = -1073741670;
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v24 = -102;
                v22 = 57;
                v23 = 11;
                goto LABEL_33;
              }
              goto LABEL_25;
            }
            *((_QWORD *)v21 + 1) = v21;
            *(_QWORD *)v21 = v21;
            *(_OWORD *)(v21 + 24) = 0;
            *((_DWORD *)v21 + 4) = v20;
            *((_DWORD *)v21 + 10) = 48;
            *((_DWORD *)v21 + 5) = -2147483522;
            v16 = FltAddOpenReparseEntry(Globals, CallbackData, v21);
            if ( v16 >= 0 )
            {
LABEL_22:
              v11[6] = FileNameInformation[0];
              FileNameInformation[0] = 0;
              v11[7] = v10;
              v11[8] = v18;
              *a3 = v11;
              v8 = 5;
              v11 = 0;
              v10 = 0;
              goto LABEL_3;
            }
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v24 = v16;
              v22 = 58;
              v23 = 29;
LABEL_33:
              LOBYTE(v15) = 2;
              WPP_RECORDER_SF_sDd(
                wil_details_featureDescriptors_a->DeviceExtension,
                v15,
                5,
                v22,
                (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
                v23,
                v24);
              CallbackData->IoStatus.Status = v16;
              v8 = 4;
              CallbackData->IoStatus.Information = 0;
              goto LABEL_3;
            }
          }
        }
        else
        {
          v16 = -1073741670;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v24 = -102;
            v22 = 53;
            v23 = -46;
            goto LABEL_33;
          }
        }
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v24 = v16;
        v22 = 52;
        v23 = -56;
        goto LABEL_33;
      }
    }
LABEL_25:
    CallbackData->IoStatus.Status = v16;
    v8 = 4;
    CallbackData->IoStatus.Information = 0;
  }
LABEL_3:
  if ( FileNameInformation[0] )
    FltReleaseFileNameInformation(FileNameInformation[0]);
  if ( v10 )
    ExFreeToPagedLookasideList(&stru_14000E380, v10);
  if ( v11 )
    ExFreeToPagedLookasideList(&stru_14000E400, v11);
  return v8;
}

```

## disassembly

```asm
0x140024380  mov     rax, rsp
0x140024383  push    rbx
0x140024384  push    rsi
0x140024385  push    rdi
0x140024386  push    r13
0x140024388  push    r14
0x14002438a  sub     rsp, 60h
0x14002438e  xor     r13d, r13d
0x140024391  mov     dword ptr [rax+10h], 0FFF0000h
0x140024398  mov     rdi, rdx
0x14002439b  mov     [rax-48h], r13
0x14002439f  mov     rdx, [rdx+20h]
0x1400243a3  mov     r14, r8
0x1400243a6  mov     rsi, rcx
0x1400243a9  mov     dword ptr [rax+20h], 0FFF0000h
0x1400243b0  mov     ebx, 1
0x1400243b5  test    dword ptr [rdx+50h], 400000h
0x1400243bc  jnz     short loc_14002441D
0x1400243be  mov     rcx, [rdi+18h]
0x1400243c2  lea     r9, [rax+20h]
0x1400243c6  mov     [rax+8], rbp
0x1400243ca  lea     r8, [rax+10h]
0x1400243ce  mov     [rax-38h], r15
0x1400243d2  mov     ebp, r13d
0x1400243d5  mov     r15d, r13d
0x1400243d8  call    WcUnionsExistForInstance
0x1400243dd  test    al, al
0x1400243df  jnz     short loc_14002442C
0x1400243e1  mov     rcx, [rsp+88h+FileNameInformation]; FileNameInformation
0x1400243e6  test    rcx, rcx
0x1400243e9  jnz     loc_1400245C5
0x1400243ef  test    rbp, rbp
0x1400243f2  jnz     loc_1400245D6
0x1400243f8  mov     rbp, [rsp+88h+arg_0]
0x140024400  test    r15, r15
0x140024403  jnz     loc_1400245F1
0x140024409  mov     r15, [rsp+88h+var_38]
0x14002440e  mov     eax, ebx
0x140024410  add     rsp, 60h
0x140024414  pop     r14
0x140024416  pop     r13
0x140024418  pop     rdi
0x140024419  pop     rsi
0x14002441a  pop     rbx
0x14002441b  retn
0x14002441d  mov     eax, ebx
0x14002441f  add     rsp, 60h
0x140024423  pop     r14
0x140024425  pop     r13
0x140024427  pop     rdi
0x140024428  pop     rsi
0x140024429  pop     rbx
0x14002442a  retn
0x14002442c  mov     [rsp+88h+var_30], r12
0x140024431  cmp     [rdi+28h], r13
0x140024435  jnz     loc_140024705
0x14002443b  mov     rcx, [rsi+10h]
0x14002443f  test    dword ptr [rcx+20h], 2000h
0x140024446  jnz     short loc_140024477
0x140024448  movzx   eax, byte ptr [rcx+6]
0x14002444c  lea     r8, [rsp+88h+FileNameInformation]; FileNameInformation
0x140024451  test    al, 4
0x140024453  jnz     loc_14002474D
0x140024459  mov     edx, 102h; NameOptions
0x14002445e  mov     rcx, rsi; CallbackData
0x140024461  call    cs:__imp_FltGetFileNameInformation
0x140024468  nop     dword ptr [rax+rax+00h]
0x14002446d  mov     edi, eax
0x14002446f  test    edi, edi
0x140024471  js      loc_140024775
0x140024477  lea     rcx, stru_14000E400; Lookaside
0x14002447e  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140024485  nop     dword ptr [rax+rax+00h]
0x14002448a  mov     r15, rax
0x14002448d  test    rax, rax
0x140024490  jz      loc_14002459E
0x140024496  mov     [rax+8], rax
0x14002449a  xorps   xmm0, xmm0
0x14002449d  mov     [rax], rax
0x1400244a0  mov     r8, r15
0x1400244a3  movups  xmmword ptr [rax+18h], xmm0
0x1400244a7  mov     eax, [rsp+88h+arg_8]
0x1400244ae  mov     rdx, rsi
0x1400244b1  mov     [r15+10h], eax
0x1400244b5  mov     dword ptr [r15+14h], 80000004h
0x1400244bd  mov     dword ptr [r15+28h], 30h ; '0'
0x1400244c5  mov     rcx, cs:Globals
0x1400244cc  call    cs:__imp_FltAddOpenReparseEntry
0x1400244d3  nop     dword ptr [rax+rax+00h]
0x1400244d8  mov     edi, eax
0x1400244da  test    eax, eax
0x1400244dc  js      loc_1400247B7
0x1400244e2  mov     rax, [rsi+10h]
0x1400244e6  mov     rbx, r13
0x1400244e9  test    dword ptr [rax+20h], 200000h
0x1400244f0  jz      short loc_14002456C
0x1400244f2  lea     rcx, stru_14000E380; Lookaside
0x1400244f9  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140024500  nop     dword ptr [rax+rax+00h]
0x140024505  mov     rbp, rax
0x140024508  test    rax, rax
0x14002450b  jz      loc_1400247E2
0x140024511  mov     [rax+8], rax
0x140024515  xorps   xmm0, xmm0
0x140024518  mov     [rax], rax
0x14002451b  mov     r8, rax
0x14002451e  movups  xmmword ptr [rax+18h], xmm0
0x140024522  mov     dword ptr [rax+10h], 0A000001Fh
0x140024529  mov     rdx, rsi
0x14002452c  mov     dword ptr [rax+28h], 30h ; '0'
0x140024533  mov     dword ptr [rax+14h], 8000007Eh
0x14002453a  mov     rcx, cs:Globals
0x140024541  call    cs:__imp_FltAddOpenReparseEntry
0x140024548  nop     dword ptr [rax+rax+00h]
0x14002454d  mov     edi, eax
0x14002454f  test    eax, eax
0x140024551  js      loc_140024812
0x140024557  mov     r12d, [rsp+88h+arg_18]
0x14002455f  test    r12d, 0FFF0000h
0x140024566  jz      loc_14002460C
0x14002456c  mov     rax, [rsp+88h+FileNameInformation]
0x140024571  mov     [r15+30h], rax
0x140024575  mov     [rsp+88h+FileNameInformation], r13
0x14002457a  mov     [r15+38h], rbp
0x14002457e  mov     [r15+40h], rbx
0x140024582  mov     [r14], r15
0x140024585  mov     ebx, 5
0x14002458a  mov     r15, r13
0x14002458d  mov     rbp, r13
0x140024590  test    edi, edi
0x140024592  js      short loc_1400245B7
0x140024594  mov     r12, [rsp+88h+var_30]
0x140024599  jmp     loc_1400243E1
0x14002459e  mov     edi, 0C000009Ah
0x1400245a3  lea     rax, WPP_RECORDER_INITIALIZED
0x1400245aa  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400245b1  jnz     loc_1400247A0
0x1400245b7  mov     [rsi+18h], edi
0x1400245ba  mov     ebx, 4
0x1400245bf  mov     [rsi+20h], r13
0x1400245c3  jmp     short loc_140024594
0x1400245c5  call    cs:__imp_FltReleaseFileNameInformation
0x1400245cc  nop     dword ptr [rax+rax+00h]
0x1400245d1  jmp     loc_1400243EF
0x1400245d6  mov     rdx, rbp; Entry
0x1400245d9  lea     rcx, stru_14000E380; Lookaside
0x1400245e0  call    cs:__imp_ExFreeToPagedLookasideList
0x1400245e7  nop     dword ptr [rax+rax+00h]
0x1400245ec  jmp     loc_1400243F8
0x1400245f1  mov     rdx, r15; Entry
0x1400245f4  lea     rcx, stru_14000E400; Lookaside
0x1400245fb  call    cs:__imp_ExFreeToPagedLookasideList
0x140024602  nop     dword ptr [rax+rax+00h]
0x140024607  jmp     loc_140024409
0x14002460c  cmp     r12d, 2
0x140024610  jbe     loc_14002456C
0x140024616  mov     eax, r12d
0x140024619  and     eax, 0C0000000h
0x14002461e  cmp     eax, 40000000h
0x140024623  jz      loc_14002456C
0x140024629  mov     eax, r12d
0x14002462c  and     eax, 30000000h
0x140024631  cmp     eax, 30000000h
0x140024636  jz      loc_14002456C
0x14002463c  lea     rcx, stru_14000E380; Lookaside
0x140024643  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14002464a  nop     dword ptr [rax+rax+00h]
0x14002464f  mov     rbx, rax
0x140024652  test    rax, rax
0x140024655  jz      loc_14002483D
0x14002465b  mov     [rax+8], rax
0x14002465f  xorps   xmm0, xmm0
0x140024662  mov     [rax], rax
0x140024665  mov     r8, rax
0x140024668  movups  xmmword ptr [rax+18h], xmm0
0x14002466c  mov     [rax+10h], r12d
0x140024670  mov     rdx, rsi
0x140024673  mov     dword ptr [rax+28h], 30h ; '0'
0x14002467a  mov     dword ptr [rax+14h], 8000007Eh
0x140024681  mov     rcx, cs:Globals
0x140024688  call    cs:__imp_FltAddOpenReparseEntry
0x14002468f  nop     dword ptr [rax+rax+00h]
0x140024694  mov     edi, eax
0x140024696  test    eax, eax
0x140024698  jns     loc_14002456C
0x14002469e  lea     rax, WPP_RECORDER_INITIALIZED
0x1400246a5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400246ac  jz      loc_1400245B7
0x1400246b2  mov     dword ptr [rsp+88h+var_50], edi
0x1400246b6  mov     r9d, 3Ah ; ':'
0x1400246bc  mov     dword ptr [rsp+88h+var_58], 0A1Dh
0x1400246c4  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400246cb  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x1400246d2  mov     [rsp+88h+var_60], rax
0x1400246d7  mov     r8d, 5
0x1400246dd  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x1400246e4  mov     dl, 2
0x1400246e6  mov     [rsp+88h+var_68], rax
0x1400246eb  mov     rcx, [rcx+40h]
0x1400246ef  call    WPP_RECORDER_SF_sDd
0x1400246f4  mov     [rsi+18h], edi
0x1400246f7  mov     ebx, 4
0x1400246fc  mov     [rsi+20h], r13
0x140024700  jmp     loc_140024594
0x140024705  mov     r8d, [rsp+88h+arg_8]
0x14002470d  mov     rdx, rdi
0x140024710  mov     rcx, rsi; CallbackData
0x140024713  call    WcPreTransaction
0x140024718  mov     edi, eax
0x14002471a  test    eax, eax
0x14002471c  jns     loc_140024594
0x140024722  lea     rax, WPP_RECORDER_INITIALIZED
0x140024729  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024730  jz      loc_1400245B7
0x140024736  mov     dword ptr [rsp+88h+var_50], edi
0x14002473a  mov     r9d, 33h ; '3'
0x140024740  mov     dword ptr [rsp+88h+var_58], 99Ch
0x140024748  jmp     loc_1400246C4
0x14002474d  and     al, 0FBh
0x14002474f  mov     edx, 302h; NameOptions
0x140024754  mov     [rcx+6], al
0x140024757  mov     rcx, rsi; CallbackData
0x14002475a  call    cs:__imp_FltGetFileNameInformation
0x140024761  nop     dword ptr [rax+rax+00h]
0x140024766  mov     edi, eax
0x140024768  mov     rax, [rsi+10h]
0x14002476c  or      byte ptr [rax+6], 4
0x140024770  jmp     loc_14002446F
0x140024775  lea     rax, WPP_RECORDER_INITIALIZED
0x14002477c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024783  jz      loc_1400245B7
0x140024789  mov     dword ptr [rsp+88h+var_50], edi
0x14002478d  mov     r9d, 34h ; '4'
0x140024793  mov     dword ptr [rsp+88h+var_58], 9C8h
0x14002479b  jmp     loc_1400246C4
0x1400247a0  mov     dword ptr [rsp+88h+var_50], edi
0x1400247a4  mov     r9d, 35h ; '5'
0x1400247aa  mov     dword ptr [rsp+88h+var_58], 9D2h
0x1400247b2  jmp     loc_1400246C4
0x1400247b7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400247be  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400247c5  jz      loc_1400245B7
0x1400247cb  mov     dword ptr [rsp+88h+var_50], edi
0x1400247cf  mov     r9d, 36h ; '6'
0x1400247d5  mov     dword ptr [rsp+88h+var_58], 9DEh
0x1400247dd  jmp     loc_1400246C4
0x1400247e2  mov     edi, 0C000009Ah
0x1400247e7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400247ee  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400247f5  jz      loc_1400245B7
0x1400247fb  mov     dword ptr [rsp+88h+var_50], edi
0x1400247ff  mov     r9d, 37h ; '7'
0x140024805  mov     dword ptr [rsp+88h+var_58], 9EEh
0x14002480d  jmp     loc_1400246C4
0x140024812  lea     rax, WPP_RECORDER_INITIALIZED
0x140024819  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024820  jz      loc_1400245B7
0x140024826  mov     dword ptr [rsp+88h+var_50], edi
0x14002482a  mov     r9d, 38h ; '8'
0x140024830  mov     dword ptr [rsp+88h+var_58], 0A00h
0x140024838  jmp     loc_1400246C4
0x14002483d  mov     edi, 0C000009Ah
0x140024842  lea     rax, WPP_RECORDER_INITIALIZED
0x140024849  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024850  jz      loc_1400245B7
0x140024856  mov     dword ptr [rsp+88h+var_50], edi
0x14002485a  mov     r9d, 39h ; '9'
0x140024860  mov     dword ptr [rsp+88h+var_58], 0A0Bh
0x140024868  jmp     loc_1400246C4
```
