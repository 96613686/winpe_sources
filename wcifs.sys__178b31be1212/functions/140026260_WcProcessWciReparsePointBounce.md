# WcProcessWciReparsePointBounce

- ea: `0x140026260`
- end: `0x140026ba0`
- name: `WcProcessWciReparsePointBounce`
- size: `2368`
- prototype: `__int64 __fastcall(struct _FLT_CALLBACK_DATA *, struct _FLT_INSTANCE *, int, struct _FLT_FILE_NAME_INFORMATION *, USHORT usSubtrahend, _DWORD *, char *, _DWORD *, struct _FILE_OBJECT **)`
- caller_count: `2`
- callee_count: `19`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x14001939c`
- `0x140025270`

## callees

- `0x140001008`
- `0x140001030`
- `0x1400016f0`
- `0x1400020c4`
- `0x140002294`
- `0x140002a88`
- `0x140004198`
- `0x14000465c`
- `0x140004b0c`
- `0x140004d7c`
- `0x140007c60`
- `0x140014ad4`
- `0x140026260`
- `0x140029658`
- `0x14002d648`
- `0x14002eea4`
- `0x14002ef90`
- `0x14002f428`
- `0x1400302cc`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140026b71`
- `ntoskrnl!ObfDereferenceObject` at `0x140026b71`
- `FLTMGR!FltClose` at `0x140026b5d`
- `FLTMGR!FltClose` at `0x140026b5d`
- `FLTMGR!FltParseFileNameInformation` at `0x1400262fd`
- `FLTMGR!FltParseFileNameInformation` at `0x1400262fd`
- `FLTMGR!FltReleaseContext` at `0x140026b22`
- `FLTMGR!FltReleaseContext` at `0x140026b37`
- `FLTMGR!FltReleaseContext` at `0x140026b22`
- `FLTMGR!FltReleaseContext` at `0x140026b37`

## string_xrefs

- `0x140026338`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140026427`: `onecore\base\fs\wci\wcifs\create.c`
- `0x1400266f7`: `onecore\base\fs\wci\wcifs\create.c`
- `0x1400267ce`: `onecore\base\fs\wci\wcifs\create.c`
- `0x14002692c`: `onecore\base\fs\wci\wcifs\create.c`
- `0x1400269cc`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140026a2a`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140026ac3`: `onecore\base\fs\wci\wcifs\create.c`

## pseudocode

```c
__int64 __fastcall WcProcessWciReparsePointBounce(
        struct _FLT_CALLBACK_DATA *a1,
        struct _FLT_INSTANCE *a2,
        int a3,
        struct _FLT_FILE_NAME_INFORMATION *a4,
        USHORT usSubtrahend,
        _DWORD *a6,
        char *a7,
        _DWORD *a8,
        struct _FILE_OBJECT **a9)
{
  NTSTATUS v10; // eax
  int v11; // ebx
  USHORT Length; // cx
  USHORT v13; // dx
  USHORT v14; // dx
  unsigned __int16 v15; // dx
  __int64 v16; // r10
  __int64 v17; // r11
  __int64 v18; // r9
  char FsInformationClass_high; // dl
  int v20; // eax
  int v21; // r8d
  int v22; // edx
  int v23; // r9d
  int v24; // edx
  int v25; // r8d
  int v26; // ecx
  int v27; // r9d
  struct _FILE_OBJECT *v28; // r14
  struct _FLT_INSTANCE *v29; // rbx
  __int64 UnionContext; // rax
  int v31; // edx
  __int64 v32; // r13
  int v33; // eax
  int SetContextFileObject; // eax
  int v35; // edx
  int v36; // eax
  int v37; // edx
  int v38; // r8d
  int v39; // eax
  int v40; // eax
  int v41; // edx
  char v42; // al
  int v44; // [rsp+20h] [rbp-E0h]
  char v45; // [rsp+50h] [rbp-B0h] BYREF
  char v46; // [rsp+51h] [rbp-AFh] BYREF
  char v47; // [rsp+52h] [rbp-AEh] BYREF
  int v48; // [rsp+54h] [rbp-ACh] BYREF
  PVOID Object; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING v51; // [rsp+68h] [rbp-98h] BYREF
  PFLT_INSTANCE Instance; // [rsp+78h] [rbp-88h]
  PFLT_CALLBACK_DATA Data; // [rsp+80h] [rbp-80h]
  USHORT pusResult[8]; // [rsp+88h] [rbp-78h] BYREF
  struct _FLT_FILE_NAME_INFORMATION *v55; // [rsp+98h] [rbp-68h]
  struct _FILE_OBJECT **v56; // [rsp+A0h] [rbp-60h]
  PFLT_CONTEXT Context; // [rsp+A8h] [rbp-58h] BYREF
  PFLT_CONTEXT v58; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v59; // [rsp+B8h] [rbp-48h] BYREF
  _DWORD *v60; // [rsp+C8h] [rbp-38h]
  _DWORD *v61; // [rsp+D0h] [rbp-30h]
  char *v62; // [rsp+D8h] [rbp-28h]
  char v63[32]; // [rsp+E0h] [rbp-20h] BYREF
  char *v64; // [rsp+100h] [rbp+0h]
  __int64 v65; // [rsp+108h] [rbp+8h]
  char *v66; // [rsp+110h] [rbp+10h]
  __int64 v67; // [rsp+118h] [rbp+18h]
  int *v68; // [rsp+120h] [rbp+20h]
  __int64 v69; // [rsp+128h] [rbp+28h]

  v61 = a8;
  Data = a1;
  v60 = a6;
  v55 = a4;
  v48 = a3;
  Instance = a2;
  v62 = a7;
  v56 = a9;
  *(_OWORD *)pusResult = 0;
  FileHandle = 0;
  Object = 0;
  v51 = 0;
  v46 = 0;
  v59 = 0;
  v45 = 0;
  Context = 0;
  v58 = 0;
  v10 = FltParseFileNameInformation(a4);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        2,
        5,
        34,
        (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
        29,
        v10);
    return (unsigned int)v11;
  }
  if ( a4->ParentDir.Length == 2 )
  {
    *a7 = 1;
    *a9 = 0;
    return (unsigned int)v11;
  }
  Length = a4->Name.Length;
  v13 = usSubtrahend + 2;
  if ( a4->Name.Buffer[((unsigned __int64)Length >> 1) - 1] != 92 )
    v13 = usSubtrahend;
  if ( v13 > Length )
    return (unsigned int)-1073741766;
  v11 = RtlUShortSub(Length, v13, pusResult);
  if ( v11 >= 0 )
  {
    v11 = RtlUShortSub(a4->Name.MaximumLength, v14, &pusResult[1]);
    if ( v11 >= 0 )
    {
      LOWORD(v59) = v15;
      WORD1(v59) = v15;
      *(_QWORD *)&pusResult[4] = v17;
      *((_QWORD *)&v59 + 1) = v17 + 2 * (v16 - ((unsigned __int64)v15 >> 1));
      v11 = WcParseNextPathComponentName(&v59, &v51, &v45);
      if ( v11 >= 0 )
      {
        if ( !v45
          || (FsInformationClass_high = HIBYTE(Data->Iopb->Parameters.SetVolumeInformation.FsInformationClass),
              FsInformationClass_high == 1)
          || FsInformationClass_high == 4 )
        {
          LOBYTE(v18) = v45;
          v20 = WcFastLookupInLayer(Instance, &Data->TagData->SymbolicLinkReparseBuffer, &v51, v18);
          v11 = v20;
          if ( v20 < 0 )
          {
            v22 = -1073741772;
            if ( v20 == -1073741772 )
            {
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                || !LOWORD(wil_details_featureDescriptors_a->DeviceType) )
              {
                return (unsigned int)v11;
              }
              v23 = 35;
              goto LABEL_21;
            }
            if ( v20 == -1073741766 )
            {
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                || !LOWORD(wil_details_featureDescriptors_a->DeviceType) )
              {
                return (unsigned int)v11;
              }
              v23 = 36;
LABEL_21:
              WPP_RECORDER_SF_sDZZd(0, -1073741772, v21, v23);
              return (unsigned int)v11;
            }
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v22) = 3;
              WPP_RECORDER_SF_sDdZ(
                wil_details_featureDescriptors_a->DeviceExtension,
                v22,
                5,
                37,
                (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
                142,
                v20,
                (__int64)pusResult);
            }
          }
        }
        v11 = WcOpenPlaceHolder(Instance, (__int64)pusResult, 0x29u, v48, &FileHandle, &Object, &v46);
        v26 = 0;
        if ( v11 < 0 )
        {
          if ( v11 == -1073741191 )
          {
            v11 = -1073741766;
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              || !LOWORD(wil_details_featureDescriptors_a->DeviceType) )
            {
              goto LABEL_34;
            }
            v27 = 38;
          }
          else
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_34;
            LOBYTE(v24) = 2;
            WPP_RECORDER_SF_sDdZ(
              wil_details_featureDescriptors_a->DeviceExtension,
              v24,
              5,
              39,
              (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
              193,
              v11,
              (__int64)pusResult);
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_34;
            v24 = 0;
            if ( !LOWORD(wil_details_featureDescriptors_a->DeviceType) )
              goto LABEL_34;
            v27 = 40;
          }
          WPP_RECORDER_SF_sDZZd(v26, v24, v25, v27);
LABEL_34:
          v28 = (struct _FILE_OBJECT *)Object;
LABEL_91:
          if ( FileHandle )
            FltClose(FileHandle);
          if ( v28 )
            ObfDereferenceObject(v28);
          return (unsigned int)v11;
        }
        v28 = (struct _FILE_OBJECT *)Object;
        if ( !v46 )
        {
          v32 = 0;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            if ( LOWORD(wil_details_featureDescriptors_a->DeviceType) )
              WPP_RECORDER_SF_sDZZd(0, v24, v25, 47);
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v24) = 4;
              WPP_RECORDER_SF_sDZ(
                wil_details_featureDescriptors_a->DeviceExtension,
                v24,
                10,
                48,
                (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
                154,
                (__int64)&v51);
            }
          }
LABEL_81:
          v39 = 0;
LABEL_82:
          *v61 = v39;
          v42 = v45;
          *v62 = v45;
          if ( v42 )
          {
            *v56 = v28;
            v28 = 0;
          }
          else
          {
            *v56 = 0;
          }
          goto LABEL_85;
        }
        v29 = Instance;
        UnionContext = WcGetUnionContext(0, Instance, Object);
        v31 = 0;
        v32 = UnionContext;
        if ( !UnionContext )
        {
          v11 = 0;
          if ( !v45 )
          {
            v11 = -1073741766;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v31) = 3;
              WPP_RECORDER_SF_sDdZ(
                wil_details_featureDescriptors_a->DeviceExtension,
                v31,
                5,
                41,
                (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
                235,
                58,
                (__int64)pusResult);
            }
            goto LABEL_91;
          }
          goto LABEL_81;
        }
        v33 = *(_DWORD *)(UnionContext + 24);
        if ( v33 == 1 )
        {
          SetContextFileObject = WcGetSetContextFileObject(v29, v28, v44, (__int64)&Context, (__int64)&v58);
          v11 = SetContextFileObject;
          if ( SetContextFileObject < 0 )
          {
            if ( SetContextFileObject != -1073741195 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v35) = 2;
                WPP_RECORDER_SF_sDdZ(
                  wil_details_featureDescriptors_a->DeviceExtension,
                  v35,
                  5,
                  42,
                  (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
                  (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
                  24,
                  SetContextFileObject,
                  (__int64)pusResult);
              }
LABEL_85:
              if ( Context )
                FltReleaseContext(Context);
              if ( v58 )
                FltReleaseContext(v58);
              if ( !v32 )
                goto LABEL_91;
              goto LABEL_90;
            }
          }
          else if ( SetContextFileObject != 260 )
          {
            v36 = WcPartiallyExpandDirectory(Data, Instance, v28, v45, &v51);
            v11 = v36;
            if ( v36 >= 0 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                && LOWORD(wil_details_featureDescriptors_a->DeviceType) )
              {
                WPP_RECORDER_SF_sDZZd(0, v37, v38, 44);
              }
            }
            else
            {
              if ( v36 == -1073741267 )
              {
                if ( *v60 < 0x14u )
                {
                  ++*v60;
                  v45 = 0;
                }
                else
                {
                  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
                    LOBYTE(v37) = 2;
                    WPP_RECORDER_SF_sD(
                      wil_details_featureDescriptors_a->DeviceExtension,
                      v37,
                      5,
                      43,
                      (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
                      (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
                      50);
                  }
                  if ( (unsigned int)dword_14000E060 > 5
                    && (unsigned __int8)tlgKeywordOn(&dword_14000E060, 0x400000000000LL) )
                  {
                    v46 = 4;
                    v64 = &v46;
                    v65 = 1;
                    v66 = &v47;
                    v47 = 8;
                    v68 = &v48;
                    v67 = 1;
                    v48 = -1073741267;
                    v69 = 4;
                    tlgWriteTransfer_EtwWriteTransfer(&dword_14000E060, word_14000B442, 0, 0, 5, v63);
                  }
                }
              }
              else if ( v36 != -1073741772 )
              {
                goto LABEL_85;
              }
              v11 = 0;
            }
            goto LABEL_58;
          }
          v11 = 0;
          goto LABEL_85;
        }
        if ( v33 == 2 )
        {
          if ( (*(_DWORD *)&Data->TagData->GenericGUIDReparseBuffer.TagGuid.Data2 & 4) != 0 )
          {
            v11 = v45 != 0 ? -1073741772 : -1073741766;
          }
          else
          {
            v40 = WcRedirectCallbackData(Data);
            v11 = v40;
            if ( v40 >= 0 )
            {
LABEL_58:
              v39 = *(_DWORD *)(v32 + 24);
              goto LABEL_82;
            }
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v41) = 2;
              WPP_RECORDER_SF_sDd(
                wil_details_featureDescriptors_a->DeviceExtension,
                v41,
                5,
                45,
                (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
                131,
                v40);
            }
          }
        }
        else
        {
          v11 = -1073741811;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v31) = 2;
            WPP_RECORDER_SF_sDdd(
              wil_details_featureDescriptors_a->DeviceExtension,
              v31,
              5,
              46,
              (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
              139,
              v33,
              13);
          }
        }
LABEL_90:
        WcReleaseUnionContext(v32);
        goto LABEL_91;
      }
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140026260  push    rbp
0x140026262  push    rbx
0x140026263  push    rsi
0x140026264  push    rdi
0x140026265  push    r12
0x140026267  push    r13
0x140026269  push    r14
0x14002626b  push    r15
0x14002626d  lea     rbp, [rsp-48h]
0x140026272  sub     rsp, 148h
0x140026279  mov     rax, cs:__security_cookie
0x140026280  xor     rax, rsp
0x140026283  mov     [rbp+80h+var_50], rax
0x140026287  mov     rax, [rbp+80h+arg_38]
0x14002628e  xor     r12d, r12d
0x140026291  mov     r14, [rbp+80h+arg_30]
0x140026298  xorps   xmm0, xmm0
0x14002629b  mov     rsi, [rbp+80h+arg_40]
0x1400262a2  xorps   xmm1, xmm1
0x1400262a5  mov     [rbp+80h+var_B0], rax
0x1400262a9  mov     rdi, r9
0x1400262ac  mov     rax, [rbp+80h+arg_28]
0x1400262b3  mov     [rbp+80h+Data], rcx
0x1400262b7  mov     rcx, r9; FileNameInformation
0x1400262ba  mov     [rbp+80h+var_B8], rax
0x1400262be  mov     [rbp+80h+var_E8], r9
0x1400262c2  mov     [rsp+180h+var_12C], r8d
0x1400262c7  mov     [rsp+180h+Instance], rdx
0x1400262cc  mov     [rbp+80h+var_A8], r14
0x1400262d0  mov     [rbp+80h+var_E0], rsi
0x1400262d4  movups  xmmword ptr [rbp+80h+pusResult], xmm0
0x1400262d8  mov     [rsp+180h+FileHandle], r12
0x1400262dd  mov     [rsp+180h+Object], r12
0x1400262e2  movups  xmmword ptr [rsp+180h+var_118.Length], xmm0
0x1400262e7  mov     [rsp+180h+var_12F], r12b
0x1400262ec  movups  [rbp+80h+var_C8], xmm1
0x1400262f0  mov     [rsp+180h+var_130], r12b
0x1400262f5  mov     [rbp+80h+Context], r12
0x1400262f9  mov     [rbp+80h+var_D0], r12
0x1400262fd  call    cs:__imp_FltParseFileNameInformation
0x140026304  nop     dword ptr [rax+rax+00h]
0x140026309  mov     ebx, eax
0x14002630b  test    eax, eax
0x14002630d  jns     short loc_14002636B
0x14002630f  lea     rdi, WPP_RECORDER_INITIALIZED
0x140026316  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002631d  jz      loc_140026B7D
0x140026323  mov     rcx, cs:wil_details_featureDescriptors_a
0x14002632a  lea     r9d, [r12+22h]
0x14002632f  mov     dword ptr [rsp+180h+var_148], eax
0x140026333  lea     edx, [r12+2]
0x140026338  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x14002633f  mov     dword ptr [rsp+180h+var_150], 61Dh
0x140026347  mov     [rsp+180h+var_158], rax
0x14002634c  lea     r8d, [r12+5]
0x140026351  mov     rcx, [rcx+40h]
0x140026355  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x14002635c  mov     qword ptr [rsp+180h+var_160], rax
0x140026361  call    WPP_RECORDER_SF_sDd
0x140026366  jmp     loc_140026B7D
0x14002636b  mov     r15d, 2
0x140026371  cmp     [rdi+68h], r15w
0x140026376  jnz     short loc_140026384
0x140026378  mov     byte ptr [r14], 1
0x14002637c  mov     [rsi], r12
0x14002637f  jmp     loc_140026B7D
0x140026384  mov     r11, [rdi+10h]
0x140026388  lea     r14, [rdi+8]
0x14002638c  movzx   ecx, word ptr [r14]; usMinuend
0x140026390  movzx   edx, [rbp+80h+usSubtrahend]
0x140026397  mov     r10d, ecx
0x14002639a  add     dx, r15w
0x14002639e  shr     r10, 1
0x1400263a1  cmp     word ptr [r11+r10*2-2], 5Ch ; '\'
0x1400263a8  cmovnz  dx, [rbp+80h+usSubtrahend]; usSubtrahend
0x1400263b0  cmp     dx, cx
0x1400263b3  jbe     short loc_1400263BF
0x1400263b5  mov     ebx, 0C000003Ah
0x1400263ba  jmp     loc_140026B7D
0x1400263bf  lea     r8, [rbp+80h+pusResult]; pusResult
0x1400263c3  call    RtlUShortSub
0x1400263c8  mov     ebx, eax
0x1400263ca  test    eax, eax
0x1400263cc  js      loc_140026B7D
0x1400263d2  movzx   ecx, word ptr [rdi+0Ah]; usMinuend
0x1400263d6  lea     r8, [rbp+80h+pusResult+2]; pusResult
0x1400263da  call    RtlUShortSub
0x1400263df  mov     ebx, eax
0x1400263e1  test    eax, eax
0x1400263e3  js      loc_140026B7D
0x1400263e9  movzx   eax, dx
0x1400263ec  lea     r8, [rsp+180h+var_130]
0x1400263f1  shr     rax, 1
0x1400263f4  lea     rcx, [rbp+80h+var_C8]
0x1400263f8  sub     r10, rax
0x1400263fb  mov     word ptr [rbp+80h+var_C8], dx
0x1400263ff  mov     word ptr [rbp+80h+var_C8+2], dx
0x140026403  lea     rdx, [rsp+180h+var_118]
0x140026408  mov     qword ptr [rbp+80h+pusResult+8], r11
0x14002640c  lea     rax, [r11+r10*2]
0x140026410  mov     qword ptr [rbp+80h+var_C8+8], rax
0x140026414  call    WcParseNextPathComponentName
0x140026419  mov     ebx, eax
0x14002641b  test    eax, eax
0x14002641d  js      loc_140026B7D
0x140026423  mov     cl, [rsp+180h+var_130]
0x140026427  lea     r13, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x14002642e  mov     r8, [rbp+80h+Data]
0x140026432  mov     r12d, 5
0x140026438  mov     [rsp+180h+var_130], cl
0x14002643c  lea     rdi, WPP_RECORDER_INITIALIZED
0x140026443  mov     esi, 0C000003Ah
0x140026448  test    cl, cl
0x14002644a  jz      short loc_140026461
0x14002644c  mov     rax, [r8+10h]
0x140026450  mov     dl, [rax+23h]
0x140026453  cmp     dl, 1
0x140026456  jz      short loc_140026461
0x140026458  cmp     dl, 4
0x14002645b  jnz     loc_140026574
0x140026461  mov     rdx, [r8+28h]
0x140026465  mov     r9b, cl
0x140026468  mov     rcx, [rsp+180h+Instance]
0x14002646d  lea     r8, [rsp+180h+var_118]
0x140026472  add     rdx, 8
0x140026476  call    WcFastLookupInLayer
0x14002647b  xor     ecx, ecx
0x14002647d  mov     ebx, eax
0x14002647f  test    eax, eax
0x140026481  jns     loc_140026574
0x140026487  mov     edx, 0C0000034h
0x14002648c  cmp     eax, edx
0x14002648e  jnz     short loc_1400264DE
0x140026490  lea     rdi, WPP_RECORDER_INITIALIZED
0x140026497  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002649e  jz      loc_140026B7D
0x1400264a4  mov     rax, cs:wil_details_featureDescriptors_a
0x1400264ab  cmp     [rax+48h], cx
0x1400264af  jz      loc_140026B7D
0x1400264b5  mov     [rsp+180h+var_138], edx
0x1400264b9  lea     rax, [rsp+180h+var_118]
0x1400264be  mov     [rsp+180h+var_140], r14
0x1400264c3  lea     r9d, [rcx+23h]
0x1400264c7  mov     [rsp+180h+var_148], rax
0x1400264cc  mov     dword ptr [rsp+180h+var_150], 675h
0x1400264d4  call    WPP_RECORDER_SF_sDZZd
0x1400264d9  jmp     loc_140026B7D
0x1400264de  cmp     ebx, esi
0x1400264e0  jnz     short loc_14002652A
0x1400264e2  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400264e9  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400264f0  jz      loc_140026B7D
0x1400264f6  mov     rax, cs:wil_details_featureDescriptors_a
0x1400264fd  cmp     [rax+48h], cx
0x140026501  jz      loc_140026B7D
0x140026507  mov     [rsp+180h+var_138], esi
0x14002650b  lea     rax, [rsp+180h+var_118]
0x140026510  mov     [rsp+180h+var_140], r14
0x140026515  mov     r9d, 24h ; '$'
0x14002651b  mov     [rsp+180h+var_148], rax
0x140026520  mov     dword ptr [rsp+180h+var_150], 681h
0x140026528  jmp     short loc_1400264D4
0x14002652a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140026531  jz      short loc_140026574
0x140026533  mov     rcx, cs:wil_details_featureDescriptors_a
0x14002653a  lea     rax, [rbp+80h+pusResult]
0x14002653e  mov     [rsp+180h+var_140], rax
0x140026543  mov     r9d, 25h ; '%'
0x140026549  mov     dword ptr [rsp+180h+var_148], ebx
0x14002654d  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140026554  mov     dword ptr [rsp+180h+var_150], 68Eh
0x14002655c  mov     r8d, r12d
0x14002655f  mov     rcx, [rcx+40h]
0x140026563  mov     dl, 3
0x140026565  mov     [rsp+180h+var_158], r13
0x14002656a  mov     qword ptr [rsp+180h+var_160], rax
0x14002656f  call    WPP_RECORDER_SF_sDdZ
0x140026574  mov     r9d, [rsp+180h+var_12C]
0x140026579  lea     rax, [rsp+180h+var_12F]
0x14002657e  mov     rcx, [rsp+180h+Instance]
0x140026583  lea     rdx, [rbp+80h+pusResult]
0x140026587  mov     [rsp+180h+var_150], rax
0x14002658c  mov     r8d, 29h ; ')'
0x140026592  lea     rax, [rsp+180h+Object]
0x140026597  mov     [rsp+180h+var_158], rax
0x14002659c  lea     rax, [rsp+180h+FileHandle]
0x1400265a1  mov     qword ptr [rsp+180h+var_160], rax; int
0x1400265a6  call    WcOpenPlaceHolder
0x1400265ab  mov     ebx, eax
0x1400265ad  xor     ecx, ecx
0x1400265af  mov     rax, [rsp+180h+FileHandle]
0x1400265b4  mov     [rsp+180h+FileHandle], rax
0x1400265b9  test    ebx, ebx
0x1400265bb  jns     loc_140026696
0x1400265c1  cmp     ebx, 0C0000279h
0x1400265c7  jnz     short loc_14002660F
0x1400265c9  mov     ebx, esi
0x1400265cb  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400265d2  jz      short loc_140026605
0x1400265d4  mov     rax, cs:wil_details_featureDescriptors_a
0x1400265db  cmp     [rax+48h], cx
0x1400265df  jz      short loc_140026605
0x1400265e1  mov     [rsp+180h+var_138], esi
0x1400265e5  lea     rax, [rsp+180h+var_118]
0x1400265ea  mov     [rsp+180h+var_140], r14
0x1400265ef  lea     r9d, [rcx+26h]
0x1400265f3  mov     [rsp+180h+var_148], rax
0x1400265f8  mov     dword ptr [rsp+180h+var_150], 6B2h
0x140026600  call    WPP_RECORDER_SF_sDZZd
0x140026605  mov     r14, [rsp+180h+Object]
0x14002660a  jmp     loc_140026B50
0x14002660f  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140026616  jz      short loc_140026605
0x140026618  mov     rcx, cs:wil_details_featureDescriptors_a
0x14002661f  lea     rax, [rbp+80h+pusResult]
0x140026623  mov     [rsp+180h+var_140], rax
0x140026628  mov     r9d, 27h ; '''
0x14002662e  mov     dword ptr [rsp+180h+var_148], ebx
0x140026632  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140026639  mov     dword ptr [rsp+180h+var_150], 6C1h
0x140026641  mov     r8d, r12d
0x140026644  mov     rcx, [rcx+40h]
0x140026648  mov     dl, r15b
0x14002664b  mov     [rsp+180h+var_158], r13
0x140026650  mov     qword ptr [rsp+180h+var_160], rax
0x140026655  call    WPP_RECORDER_SF_sDdZ
0x14002665a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140026661  jz      short loc_140026605
0x140026663  mov     rax, cs:wil_details_featureDescriptors_a
0x14002666a  xor     edx, edx
0x14002666c  cmp     [rax+48h], dx
0x140026670  jz      short loc_140026605
0x140026672  mov     [rsp+180h+var_138], ebx
0x140026676  lea     rax, [rsp+180h+var_118]
0x14002667b  mov     [rsp+180h+var_140], r14
0x140026680  lea     r9d, [rdx+28h]
0x140026684  mov     [rsp+180h+var_148], rax
0x140026689  mov     dword ptr [rsp+180h+var_150], 6C2h
0x140026691  jmp     loc_140026600
0x140026696  mov     r14, [rsp+180h+Object]
0x14002669b  cmp     [rsp+180h+var_12F], cl
0x14002669f  jz      loc_140026A58
0x1400266a5  mov     rbx, [rsp+180h+Instance]
0x1400266aa  mov     r8, r14
0x1400266ad  mov     rdx, rbx
0x1400266b0  call    WcGetUnionContext
0x1400266b5  xor     edx, edx
0x1400266b7  mov     r13, rax
0x1400266ba  test    rax, rax
0x1400266bd  jnz     short loc_140026725
0x1400266bf  xor     ebx, ebx
0x1400266c1  cmp     [rsp+180h+var_130], dl
0x1400266c5  jnz     loc_140026AF2
0x1400266cb  mov     ebx, esi
0x1400266cd  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400266d4  jz      loc_140026B50
0x1400266da  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400266e1  lea     r9d, [rax+29h]
0x1400266e5  lea     rax, [rbp+80h+pusResult]
0x1400266e9  mov     r8d, r12d
0x1400266ec  mov     [rsp+180h+var_140], rax
0x1400266f1  mov     dl, 3
0x1400266f3  mov     dword ptr [rsp+180h+var_148], esi
0x1400266f7  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x1400266fe  mov     rcx, [rcx+40h]
0x140026702  mov     dword ptr [rsp+180h+var_150], 6EBh
0x14002670a  mov     [rsp+180h+var_158], rax
0x14002670f  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140026716  mov     qword ptr [rsp+180h+var_160], rax
0x14002671b  call    WPP_RECORDER_SF_sDdZ
0x140026720  jmp     loc_140026B50
0x140026725  mov     eax, [rax+18h]
0x140026728  cmp     eax, 1
0x14002672b  jnz     loc_140026967
0x140026731  lea     rax, [rbp+80h+var_D0]
0x140026735  mov     esi, 1
0x14002673a  mov     [rsp+180h+var_150], rax; __int64
0x14002673f  mov     r9d, esi
0x140026742  lea     rax, [rbp+80h+Context]
0x140026746  mov     r8, r13
0x140026749  mov     rdx, r14; FileObject
0x14002674c  mov     [rsp+180h+var_158], rax; __int64
0x140026751  mov     rcx, rbx; Instance
0x140026754  call    WcGetSetContextFileObject
0x140026759  xor     ecx, ecx
0x14002675b  mov     ebx, eax
0x14002675d  test    eax, eax
0x14002675f  js      loc_1400268FD
0x140026765  cmp     eax, 104h
0x14002676a  jz      loc_140026960
0x140026770  mov     r9, [rsp+180h+FileHandle]
0x140026775  lea     rax, [rsp+180h+var_118]
0x14002677a  mov     rdx, [rsp+180h+Instance]; FltObject
0x14002677f  mov     r8, r14; Object
0x140026782  mov     rcx, [rbp+80h+Data]; CallbackData
0x140026786  mov     [rsp+180h+var_158], rax; PUNICODE_STRING
0x14002678b  mov     al, [rsp+180h+var_130]
0x14002678f  mov     [rsp+180h+var_160], al; char
0x140026793  call    WcPartiallyExpandDirectory
0x140026798  xor     ecx, ecx
  ... truncated ...
```
