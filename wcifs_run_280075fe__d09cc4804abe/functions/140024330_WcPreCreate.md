# WcPreCreate

- ea: `0x140024330`
- end: `0x14002481d`
- name: `WcPreCreate`
- size: `1261`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callees

- `0x140001580`
- `0x1400020c4`
- `0x140024330`
- `0x1400303e8`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140024590`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400245ab`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140024590`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400245ab`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14002442e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400244a9`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400245f3`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14002442e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400244a9`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400245f3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140024575`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140024575`
- `FLTMGR!FltGetFileNameInformation` at `0x140024411`
- `FLTMGR!FltGetFileNameInformation` at `0x14002470a`
- `FLTMGR!FltGetFileNameInformation` at `0x140024411`
- `FLTMGR!FltGetFileNameInformation` at `0x14002470a`
- `FLTMGR!FltAddOpenReparseEntry` at `0x14002447c`
- `FLTMGR!FltAddOpenReparseEntry` at `0x1400244f1`
- `FLTMGR!FltAddOpenReparseEntry` at `0x140024638`
- `FLTMGR!FltAddOpenReparseEntry` at `0x14002447c`
- `FLTMGR!FltAddOpenReparseEntry` at `0x1400244f1`
- `FLTMGR!FltAddOpenReparseEntry` at `0x140024638`

## string_xrefs

- `0x14002467b`: `onecore\base\fs\wci\wcifs\create.c`

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
                WPP_GLOBAL_Control->DeviceExtension,
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
0x140024330  mov     rax, rsp
0x140024333  push    rbx
0x140024334  push    rsi
0x140024335  push    rdi
0x140024336  push    r13
0x140024338  push    r14
0x14002433a  sub     rsp, 60h
0x14002433e  xor     r13d, r13d
0x140024341  mov     dword ptr [rax+10h], 0FFF0000h
0x140024348  mov     rdi, rdx
0x14002434b  mov     [rax-48h], r13
0x14002434f  mov     rdx, [rdx+20h]
0x140024353  mov     r14, r8
0x140024356  mov     rsi, rcx
0x140024359  mov     dword ptr [rax+20h], 0FFF0000h
0x140024360  mov     ebx, 1
0x140024365  test    dword ptr [rdx+50h], 400000h
0x14002436c  jnz     short loc_1400243CD
0x14002436e  mov     rcx, [rdi+18h]
0x140024372  lea     r9, [rax+20h]
0x140024376  mov     [rax+8], rbp
0x14002437a  lea     r8, [rax+10h]
0x14002437e  mov     [rax-38h], r15
0x140024382  mov     ebp, r13d
0x140024385  mov     r15d, r13d
0x140024388  call    WcUnionsExistForInstance
0x14002438d  test    al, al
0x14002438f  jnz     short loc_1400243DC
0x140024391  mov     rcx, [rsp+88h+FileNameInformation]; FileNameInformation
0x140024396  test    rcx, rcx
0x140024399  jnz     loc_140024575
0x14002439f  test    rbp, rbp
0x1400243a2  jnz     loc_140024586
0x1400243a8  mov     rbp, [rsp+88h+arg_0]
0x1400243b0  test    r15, r15
0x1400243b3  jnz     loc_1400245A1
0x1400243b9  mov     r15, [rsp+88h+var_38]
0x1400243be  mov     eax, ebx
0x1400243c0  add     rsp, 60h
0x1400243c4  pop     r14
0x1400243c6  pop     r13
0x1400243c8  pop     rdi
0x1400243c9  pop     rsi
0x1400243ca  pop     rbx
0x1400243cb  retn
0x1400243cd  mov     eax, ebx
0x1400243cf  add     rsp, 60h
0x1400243d3  pop     r14
0x1400243d5  pop     r13
0x1400243d7  pop     rdi
0x1400243d8  pop     rsi
0x1400243d9  pop     rbx
0x1400243da  retn
0x1400243dc  mov     [rsp+88h+var_30], r12
0x1400243e1  cmp     [rdi+28h], r13
0x1400243e5  jnz     loc_1400246B5
0x1400243eb  mov     rcx, [rsi+10h]
0x1400243ef  test    dword ptr [rcx+20h], 2000h
0x1400243f6  jnz     short loc_140024427
0x1400243f8  movzx   eax, byte ptr [rcx+6]
0x1400243fc  lea     r8, [rsp+88h+FileNameInformation]; FileNameInformation
0x140024401  test    al, 4
0x140024403  jnz     loc_1400246FD
0x140024409  mov     edx, 102h; NameOptions
0x14002440e  mov     rcx, rsi; CallbackData
0x140024411  call    cs:__imp_FltGetFileNameInformation
0x140024418  nop     dword ptr [rax+rax+00h]
0x14002441d  mov     edi, eax
0x14002441f  test    edi, edi
0x140024421  js      loc_140024725
0x140024427  lea     rcx, stru_14000E400; Lookaside
0x14002442e  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140024435  nop     dword ptr [rax+rax+00h]
0x14002443a  mov     r15, rax
0x14002443d  test    rax, rax
0x140024440  jz      loc_14002454E
0x140024446  mov     [rax+8], rax
0x14002444a  xorps   xmm0, xmm0
0x14002444d  mov     [rax], rax
0x140024450  mov     r8, r15
0x140024453  movups  xmmword ptr [rax+18h], xmm0
0x140024457  mov     eax, [rsp+88h+arg_8]
0x14002445e  mov     rdx, rsi
0x140024461  mov     [r15+10h], eax
0x140024465  mov     dword ptr [r15+14h], 80000004h
0x14002446d  mov     dword ptr [r15+28h], 30h ; '0'
0x140024475  mov     rcx, cs:Globals
0x14002447c  call    cs:__imp_FltAddOpenReparseEntry
0x140024483  nop     dword ptr [rax+rax+00h]
0x140024488  mov     edi, eax
0x14002448a  test    eax, eax
0x14002448c  js      loc_140024767
0x140024492  mov     rax, [rsi+10h]
0x140024496  mov     rbx, r13
0x140024499  test    dword ptr [rax+20h], 200000h
0x1400244a0  jz      short loc_14002451C
0x1400244a2  lea     rcx, stru_14000E380; Lookaside
0x1400244a9  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400244b0  nop     dword ptr [rax+rax+00h]
0x1400244b5  mov     rbp, rax
0x1400244b8  test    rax, rax
0x1400244bb  jz      loc_140024792
0x1400244c1  mov     [rax+8], rax
0x1400244c5  xorps   xmm0, xmm0
0x1400244c8  mov     [rax], rax
0x1400244cb  mov     r8, rax
0x1400244ce  movups  xmmword ptr [rax+18h], xmm0
0x1400244d2  mov     dword ptr [rax+10h], 0A000001Fh
0x1400244d9  mov     rdx, rsi
0x1400244dc  mov     dword ptr [rax+28h], 30h ; '0'
0x1400244e3  mov     dword ptr [rax+14h], 8000007Eh
0x1400244ea  mov     rcx, cs:Globals
0x1400244f1  call    cs:__imp_FltAddOpenReparseEntry
0x1400244f8  nop     dword ptr [rax+rax+00h]
0x1400244fd  mov     edi, eax
0x1400244ff  test    eax, eax
0x140024501  js      loc_1400247C2
0x140024507  mov     r12d, [rsp+88h+arg_18]
0x14002450f  test    r12d, 0FFF0000h
0x140024516  jz      loc_1400245BC
0x14002451c  mov     rax, [rsp+88h+FileNameInformation]
0x140024521  mov     [r15+30h], rax
0x140024525  mov     [rsp+88h+FileNameInformation], r13
0x14002452a  mov     [r15+38h], rbp
0x14002452e  mov     [r15+40h], rbx
0x140024532  mov     [r14], r15
0x140024535  mov     ebx, 5
0x14002453a  mov     r15, r13
0x14002453d  mov     rbp, r13
0x140024540  test    edi, edi
0x140024542  js      short loc_140024567
0x140024544  mov     r12, [rsp+88h+var_30]
0x140024549  jmp     loc_140024391
0x14002454e  mov     edi, 0C000009Ah
0x140024553  lea     rax, WPP_RECORDER_INITIALIZED
0x14002455a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024561  jnz     loc_140024750
0x140024567  mov     [rsi+18h], edi
0x14002456a  mov     ebx, 4
0x14002456f  mov     [rsi+20h], r13
0x140024573  jmp     short loc_140024544
0x140024575  call    cs:__imp_FltReleaseFileNameInformation
0x14002457c  nop     dword ptr [rax+rax+00h]
0x140024581  jmp     loc_14002439F
0x140024586  mov     rdx, rbp; Entry
0x140024589  lea     rcx, stru_14000E380; Lookaside
0x140024590  call    cs:__imp_ExFreeToPagedLookasideList
0x140024597  nop     dword ptr [rax+rax+00h]
0x14002459c  jmp     loc_1400243A8
0x1400245a1  mov     rdx, r15; Entry
0x1400245a4  lea     rcx, stru_14000E400; Lookaside
0x1400245ab  call    cs:__imp_ExFreeToPagedLookasideList
0x1400245b2  nop     dword ptr [rax+rax+00h]
0x1400245b7  jmp     loc_1400243B9
0x1400245bc  cmp     r12d, 2
0x1400245c0  jbe     loc_14002451C
0x1400245c6  mov     eax, r12d
0x1400245c9  and     eax, 0C0000000h
0x1400245ce  cmp     eax, 40000000h
0x1400245d3  jz      loc_14002451C
0x1400245d9  mov     eax, r12d
0x1400245dc  and     eax, 30000000h
0x1400245e1  cmp     eax, 30000000h
0x1400245e6  jz      loc_14002451C
0x1400245ec  lea     rcx, stru_14000E380; Lookaside
0x1400245f3  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400245fa  nop     dword ptr [rax+rax+00h]
0x1400245ff  mov     rbx, rax
0x140024602  test    rax, rax
0x140024605  jz      loc_1400247ED
0x14002460b  mov     [rax+8], rax
0x14002460f  xorps   xmm0, xmm0
0x140024612  mov     [rax], rax
0x140024615  mov     r8, rax
0x140024618  movups  xmmword ptr [rax+18h], xmm0
0x14002461c  mov     [rax+10h], r12d
0x140024620  mov     rdx, rsi
0x140024623  mov     dword ptr [rax+28h], 30h ; '0'
0x14002462a  mov     dword ptr [rax+14h], 8000007Eh
0x140024631  mov     rcx, cs:Globals
0x140024638  call    cs:__imp_FltAddOpenReparseEntry
0x14002463f  nop     dword ptr [rax+rax+00h]
0x140024644  mov     edi, eax
0x140024646  test    eax, eax
0x140024648  jns     loc_14002451C
0x14002464e  lea     rax, WPP_RECORDER_INITIALIZED
0x140024655  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002465c  jz      loc_140024567
0x140024662  mov     dword ptr [rsp+88h+var_50], edi
0x140024666  mov     r9d, 3Ah ; ':'
0x14002466c  mov     dword ptr [rsp+88h+var_58], 0A1Dh
0x140024674  mov     rcx, cs:WPP_GLOBAL_Control
0x14002467b  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140024682  mov     [rsp+88h+var_60], rax
0x140024687  mov     r8d, 5
0x14002468d  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140024694  mov     dl, 2
0x140024696  mov     [rsp+88h+var_68], rax
0x14002469b  mov     rcx, [rcx+40h]
0x14002469f  call    WPP_RECORDER_SF_sDd
0x1400246a4  mov     [rsi+18h], edi
0x1400246a7  mov     ebx, 4
0x1400246ac  mov     [rsi+20h], r13
0x1400246b0  jmp     loc_140024544
0x1400246b5  mov     r8d, [rsp+88h+arg_8]
0x1400246bd  mov     rdx, rdi
0x1400246c0  mov     rcx, rsi; CallbackData
0x1400246c3  call    WcPreTransaction
0x1400246c8  mov     edi, eax
0x1400246ca  test    eax, eax
0x1400246cc  jns     loc_140024544
0x1400246d2  lea     rax, WPP_RECORDER_INITIALIZED
0x1400246d9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400246e0  jz      loc_140024567
0x1400246e6  mov     dword ptr [rsp+88h+var_50], edi
0x1400246ea  mov     r9d, 33h ; '3'
0x1400246f0  mov     dword ptr [rsp+88h+var_58], 99Ch
0x1400246f8  jmp     loc_140024674
0x1400246fd  and     al, 0FBh
0x1400246ff  mov     edx, 302h; NameOptions
0x140024704  mov     [rcx+6], al
0x140024707  mov     rcx, rsi; CallbackData
0x14002470a  call    cs:__imp_FltGetFileNameInformation
0x140024711  nop     dword ptr [rax+rax+00h]
0x140024716  mov     edi, eax
0x140024718  mov     rax, [rsi+10h]
0x14002471c  or      byte ptr [rax+6], 4
0x140024720  jmp     loc_14002441F
0x140024725  lea     rax, WPP_RECORDER_INITIALIZED
0x14002472c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024733  jz      loc_140024567
0x140024739  mov     dword ptr [rsp+88h+var_50], edi
0x14002473d  mov     r9d, 34h ; '4'
0x140024743  mov     dword ptr [rsp+88h+var_58], 9C8h
0x14002474b  jmp     loc_140024674
0x140024750  mov     dword ptr [rsp+88h+var_50], edi
0x140024754  mov     r9d, 35h ; '5'
0x14002475a  mov     dword ptr [rsp+88h+var_58], 9D2h
0x140024762  jmp     loc_140024674
0x140024767  lea     rax, WPP_RECORDER_INITIALIZED
0x14002476e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024775  jz      loc_140024567
0x14002477b  mov     dword ptr [rsp+88h+var_50], edi
0x14002477f  mov     r9d, 36h ; '6'
0x140024785  mov     dword ptr [rsp+88h+var_58], 9DEh
0x14002478d  jmp     loc_140024674
0x140024792  mov     edi, 0C000009Ah
0x140024797  lea     rax, WPP_RECORDER_INITIALIZED
0x14002479e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400247a5  jz      loc_140024567
0x1400247ab  mov     dword ptr [rsp+88h+var_50], edi
0x1400247af  mov     r9d, 37h ; '7'
0x1400247b5  mov     dword ptr [rsp+88h+var_58], 9EEh
0x1400247bd  jmp     loc_140024674
0x1400247c2  lea     rax, WPP_RECORDER_INITIALIZED
0x1400247c9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400247d0  jz      loc_140024567
0x1400247d6  mov     dword ptr [rsp+88h+var_50], edi
0x1400247da  mov     r9d, 38h ; '8'
0x1400247e0  mov     dword ptr [rsp+88h+var_58], 0A00h
0x1400247e8  jmp     loc_140024674
0x1400247ed  mov     edi, 0C000009Ah
0x1400247f2  lea     rax, WPP_RECORDER_INITIALIZED
0x1400247f9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024800  jz      loc_140024567
0x140024806  mov     dword ptr [rsp+88h+var_50], edi
0x14002480a  mov     r9d, 39h ; '9'
0x140024810  mov     dword ptr [rsp+88h+var_58], 0A0Bh
0x140024818  jmp     loc_140024674
```
