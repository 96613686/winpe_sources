# WcProcessWciReparsePointBounce

- ea: `0x140026210`
- end: `0x140026b50`
- name: `WcProcessWciReparsePointBounce`
- size: `2368`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x14001939c`
- `0x140025220`

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
- `0x140026210`
- `0x140029608`
- `0x14002d5f8`
- `0x14002ee54`
- `0x14002ef40`
- `0x14002f3d8`
- `0x14003027c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140026b21`
- `ntoskrnl!ObfDereferenceObject` at `0x140026b21`
- `FLTMGR!FltClose` at `0x140026b0d`
- `FLTMGR!FltClose` at `0x140026b0d`
- `FLTMGR!FltParseFileNameInformation` at `0x1400262ad`
- `FLTMGR!FltParseFileNameInformation` at `0x1400262ad`
- `FLTMGR!FltReleaseContext` at `0x140026ad2`
- `FLTMGR!FltReleaseContext` at `0x140026ae7`
- `FLTMGR!FltReleaseContext` at `0x140026ad2`
- `FLTMGR!FltReleaseContext` at `0x140026ae7`

## string_xrefs

- `0x1400262e8`: `onecore\base\fs\wci\wcifs\create.c`
- `0x1400263d7`: `onecore\base\fs\wci\wcifs\create.c`
- `0x1400266a7`: `onecore\base\fs\wci\wcifs\create.c`
- `0x14002677e`: `onecore\base\fs\wci\wcifs\create.c`
- `0x1400268dc`: `onecore\base\fs\wci\wcifs\create.c`
- `0x14002697c`: `onecore\base\fs\wci\wcifs\create.c`
- `0x1400269da`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140026a73`: `onecore\base\fs\wci\wcifs\create.c`

## pseudocode

```c
__int64 __fastcall WcProcessWciReparsePointBounce(
        struct _FLT_CALLBACK_DATA *a1,
        struct _FLT_INSTANCE *a2,
        unsigned int a3,
        struct _FLT_FILE_NAME_INFORMATION *a4,
        USHORT usSubtrahend,
        _DWORD *a6,
        char *a7,
        _DWORD *a8,
        struct _FILE_OBJECT **a9)
{
  NTSTATUS v10; // eax
  NTSTATUS v11; // ebx
  USHORT Length; // cx
  USHORT v13; // dx
  USHORT v14; // dx
  USHORT v15; // dx
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
  char v44; // [rsp+50h] [rbp-B0h] BYREF
  char v45; // [rsp+51h] [rbp-AFh] BYREF
  char v46; // [rsp+52h] [rbp-AEh] BYREF
  unsigned int v47; // [rsp+54h] [rbp-ACh] BYREF
  PVOID Object; // [rsp+58h] [rbp-A8h]
  HANDLE FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING v50; // [rsp+68h] [rbp-98h] BYREF
  PFLT_INSTANCE Instance; // [rsp+78h] [rbp-88h]
  PFLT_CALLBACK_DATA Data; // [rsp+80h] [rbp-80h]
  USHORT pusResult[8]; // [rsp+88h] [rbp-78h] BYREF
  struct _FLT_FILE_NAME_INFORMATION *v54; // [rsp+98h] [rbp-68h]
  struct _FILE_OBJECT **v55; // [rsp+A0h] [rbp-60h]
  PFLT_CONTEXT Context; // [rsp+A8h] [rbp-58h] BYREF
  PFLT_CONTEXT v57; // [rsp+B0h] [rbp-50h] BYREF
  UNICODE_STRING v58; // [rsp+B8h] [rbp-48h] BYREF
  _DWORD *v59; // [rsp+C8h] [rbp-38h]
  _DWORD *v60; // [rsp+D0h] [rbp-30h]
  char *v61; // [rsp+D8h] [rbp-28h]
  char v62[32]; // [rsp+E0h] [rbp-20h] BYREF
  char *v63; // [rsp+100h] [rbp+0h]
  __int64 v64; // [rsp+108h] [rbp+8h]
  char *v65; // [rsp+110h] [rbp+10h]
  __int64 v66; // [rsp+118h] [rbp+18h]
  unsigned int *v67; // [rsp+120h] [rbp+20h]
  __int64 v68; // [rsp+128h] [rbp+28h]

  v60 = a8;
  Data = a1;
  v59 = a6;
  v54 = a4;
  v47 = a3;
  Instance = a2;
  v61 = a7;
  v55 = a9;
  *(_OWORD *)pusResult = 0;
  FileHandle = 0;
  Object = 0;
  v50 = 0;
  v45 = 0;
  v58 = 0;
  v44 = 0;
  Context = 0;
  v57 = 0;
  v10 = FltParseFileNameInformation(a4);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
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
      v58.Length = v15;
      v58.MaximumLength = v15;
      *(_QWORD *)&pusResult[4] = v17;
      v58.Buffer = (PWSTR)(v17 + 2 * (v16 - ((unsigned __int64)v15 >> 1)));
      v11 = WcParseNextPathComponentName(&v58, &v50, &v44);
      if ( v11 >= 0 )
      {
        if ( !v44
          || (FsInformationClass_high = HIBYTE(Data->Iopb->Parameters.SetVolumeInformation.FsInformationClass),
              FsInformationClass_high == 1)
          || FsInformationClass_high == 4 )
        {
          LOBYTE(v18) = v44;
          v20 = WcFastLookupInLayer(Instance, &Data->TagData->SymbolicLinkReparseBuffer, &v50, v18);
          v11 = v20;
          if ( v20 < 0 )
          {
            v22 = -1073741772;
            if ( v20 == -1073741772 )
            {
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
              {
                return (unsigned int)v11;
              }
              v23 = 35;
              goto LABEL_21;
            }
            if ( v20 == -1073741766 )
            {
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
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
                WPP_GLOBAL_Control->DeviceExtension,
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
        v11 = WcOpenPlaceHolder(Instance, pusResult, 41, v47);
        v26 = 0;
        if ( v11 < 0 )
        {
          if ( v11 == -1073741191 )
          {
            v11 = -1073741766;
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
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
              WPP_GLOBAL_Control->DeviceExtension,
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
            if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
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
        if ( !v45 )
        {
          v32 = 0;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
              WPP_RECORDER_SF_sDZZd(0, v24, v25, 47);
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v24) = 4;
              WPP_RECORDER_SF_sDZ(
                WPP_GLOBAL_Control->DeviceExtension,
                v24,
                10,
                48,
                (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
                154,
                (__int64)&v50);
            }
          }
LABEL_81:
          v39 = 0;
LABEL_82:
          *v60 = v39;
          v42 = v44;
          *v61 = v44;
          if ( v42 )
          {
            *v55 = v28;
            v28 = 0;
          }
          else
          {
            *v55 = 0;
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
          if ( !v44 )
          {
            v11 = -1073741766;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v31) = 3;
              WPP_RECORDER_SF_sDdZ(
                WPP_GLOBAL_Control->DeviceExtension,
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
          SetContextFileObject = WcGetSetContextFileObject(v29, v28, (int)&FileHandle, (__int64)&Context, (__int64)&v57);
          v11 = SetContextFileObject;
          if ( SetContextFileObject < 0 )
          {
            if ( SetContextFileObject != -1073741195 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v35) = 2;
                WPP_RECORDER_SF_sDdZ(
                  WPP_GLOBAL_Control->DeviceExtension,
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
              if ( v57 )
                FltReleaseContext(v57);
              if ( !v32 )
                goto LABEL_91;
              goto LABEL_90;
            }
          }
          else if ( SetContextFileObject != 260 )
          {
            v36 = WcPartiallyExpandDirectory(Data, Instance, v28, v44, &v50);
            v11 = v36;
            if ( v36 >= 0 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                && LOWORD(WPP_GLOBAL_Control->DeviceType) )
              {
                WPP_RECORDER_SF_sDZZd(0, v37, v38, 44);
              }
            }
            else
            {
              if ( v36 == -1073741267 )
              {
                if ( *v59 < 0x14u )
                {
                  ++*v59;
                  v44 = 0;
                }
                else
                {
                  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
                    LOBYTE(v37) = 2;
                    WPP_RECORDER_SF_sD(
                      WPP_GLOBAL_Control->DeviceExtension,
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
                    v45 = 4;
                    v63 = &v45;
                    v64 = 1;
                    v65 = &v46;
                    v46 = 8;
                    v67 = &v47;
                    v66 = 1;
                    v47 = -1073741267;
                    v68 = 4;
                    tlgWriteTransfer_EtwWriteTransfer(&dword_14000E060, word_14000B442, 0, 0, 5, v62);
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
            v11 = v44 != 0 ? -1073741772 : -1073741766;
          }
          else
          {
            v40 = WcRedirectCallbackData(Data, v32, &v58);
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
                WPP_GLOBAL_Control->DeviceExtension,
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
              WPP_GLOBAL_Control->DeviceExtension,
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
0x140026210  push    rbp
0x140026212  push    rbx
0x140026213  push    rsi
0x140026214  push    rdi
0x140026215  push    r12
0x140026217  push    r13
0x140026219  push    r14
0x14002621b  push    r15
0x14002621d  lea     rbp, [rsp-48h]
0x140026222  sub     rsp, 148h
0x140026229  mov     rax, cs:__security_cookie
0x140026230  xor     rax, rsp
0x140026233  mov     [rbp+80h+var_50], rax
0x140026237  mov     rax, [rbp+80h+arg_38]
0x14002623e  xor     r12d, r12d
0x140026241  mov     r14, [rbp+80h+arg_30]
0x140026248  xorps   xmm0, xmm0
0x14002624b  mov     rsi, [rbp+80h+arg_40]
0x140026252  xorps   xmm1, xmm1
0x140026255  mov     [rbp+80h+var_B0], rax
0x140026259  mov     rdi, r9
0x14002625c  mov     rax, [rbp+80h+arg_28]
0x140026263  mov     [rbp+80h+Data], rcx
0x140026267  mov     rcx, r9; FileNameInformation
0x14002626a  mov     [rbp+80h+var_B8], rax
0x14002626e  mov     [rbp+80h+var_E8], r9
0x140026272  mov     [rsp+180h+var_12C], r8d
0x140026277  mov     [rsp+180h+Instance], rdx
0x14002627c  mov     [rbp+80h+var_A8], r14
0x140026280  mov     [rbp+80h+var_E0], rsi
0x140026284  movups  xmmword ptr [rbp+80h+pusResult], xmm0
0x140026288  mov     [rsp+180h+FileHandle], r12
0x14002628d  mov     [rsp+180h+Object], r12
0x140026292  movups  xmmword ptr [rsp+180h+var_118.Length], xmm0
0x140026297  mov     [rsp+180h+var_12F], r12b
0x14002629c  movups  [rbp+80h+var_C8], xmm1
0x1400262a0  mov     [rsp+180h+var_130], r12b
0x1400262a5  mov     [rbp+80h+Context], r12
0x1400262a9  mov     [rbp+80h+var_D0], r12
0x1400262ad  call    cs:__imp_FltParseFileNameInformation
0x1400262b4  nop     dword ptr [rax+rax+00h]
0x1400262b9  mov     ebx, eax
0x1400262bb  test    eax, eax
0x1400262bd  jns     short loc_14002631B
0x1400262bf  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400262c6  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400262cd  jz      loc_140026B2D
0x1400262d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400262da  lea     r9d, [r12+22h]
0x1400262df  mov     dword ptr [rsp+180h+var_148], eax
0x1400262e3  lea     edx, [r12+2]
0x1400262e8  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x1400262ef  mov     dword ptr [rsp+180h+var_150], 61Dh
0x1400262f7  mov     [rsp+180h+var_158], rax
0x1400262fc  lea     r8d, [r12+5]
0x140026301  mov     rcx, [rcx+40h]
0x140026305  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x14002630c  mov     qword ptr [rsp+180h+var_160], rax
0x140026311  call    WPP_RECORDER_SF_sDd
0x140026316  jmp     loc_140026B2D
0x14002631b  mov     r15d, 2
0x140026321  cmp     [rdi+68h], r15w
0x140026326  jnz     short loc_140026334
0x140026328  mov     byte ptr [r14], 1
0x14002632c  mov     [rsi], r12
0x14002632f  jmp     loc_140026B2D
0x140026334  mov     r11, [rdi+10h]
0x140026338  lea     r14, [rdi+8]
0x14002633c  movzx   ecx, word ptr [r14]; usMinuend
0x140026340  movzx   edx, [rbp+80h+usSubtrahend]
0x140026347  mov     r10d, ecx
0x14002634a  add     dx, r15w
0x14002634e  shr     r10, 1
0x140026351  cmp     word ptr [r11+r10*2-2], 5Ch ; '\'
0x140026358  cmovnz  dx, [rbp+80h+usSubtrahend]; usSubtrahend
0x140026360  cmp     dx, cx
0x140026363  jbe     short loc_14002636F
0x140026365  mov     ebx, 0C000003Ah
0x14002636a  jmp     loc_140026B2D
0x14002636f  lea     r8, [rbp+80h+pusResult]; pusResult
0x140026373  call    RtlUShortSub
0x140026378  mov     ebx, eax
0x14002637a  test    eax, eax
0x14002637c  js      loc_140026B2D
0x140026382  movzx   ecx, word ptr [rdi+0Ah]; usMinuend
0x140026386  lea     r8, [rbp+80h+pusResult+2]; pusResult
0x14002638a  call    RtlUShortSub
0x14002638f  mov     ebx, eax
0x140026391  test    eax, eax
0x140026393  js      loc_140026B2D
0x140026399  movzx   eax, dx
0x14002639c  lea     r8, [rsp+180h+var_130]
0x1400263a1  shr     rax, 1
0x1400263a4  lea     rcx, [rbp+80h+var_C8]
0x1400263a8  sub     r10, rax
0x1400263ab  mov     word ptr [rbp+80h+var_C8], dx
0x1400263af  mov     word ptr [rbp+80h+var_C8+2], dx
0x1400263b3  lea     rdx, [rsp+180h+var_118]
0x1400263b8  mov     qword ptr [rbp+80h+pusResult+8], r11
0x1400263bc  lea     rax, [r11+r10*2]
0x1400263c0  mov     qword ptr [rbp+80h+var_C8+8], rax
0x1400263c4  call    WcParseNextPathComponentName
0x1400263c9  mov     ebx, eax
0x1400263cb  test    eax, eax
0x1400263cd  js      loc_140026B2D
0x1400263d3  mov     cl, [rsp+180h+var_130]
0x1400263d7  lea     r13, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x1400263de  mov     r8, [rbp+80h+Data]
0x1400263e2  mov     r12d, 5
0x1400263e8  mov     [rsp+180h+var_130], cl
0x1400263ec  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400263f3  mov     esi, 0C000003Ah
0x1400263f8  test    cl, cl
0x1400263fa  jz      short loc_140026411
0x1400263fc  mov     rax, [r8+10h]
0x140026400  mov     dl, [rax+23h]
0x140026403  cmp     dl, 1
0x140026406  jz      short loc_140026411
0x140026408  cmp     dl, 4
0x14002640b  jnz     loc_140026524
0x140026411  mov     rdx, [r8+28h]
0x140026415  mov     r9b, cl
0x140026418  mov     rcx, [rsp+180h+Instance]
0x14002641d  lea     r8, [rsp+180h+var_118]
0x140026422  add     rdx, 8
0x140026426  call    WcFastLookupInLayer
0x14002642b  xor     ecx, ecx
0x14002642d  mov     ebx, eax
0x14002642f  test    eax, eax
0x140026431  jns     loc_140026524
0x140026437  mov     edx, 0C0000034h
0x14002643c  cmp     eax, edx
0x14002643e  jnz     short loc_14002648E
0x140026440  lea     rdi, WPP_RECORDER_INITIALIZED
0x140026447  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002644e  jz      loc_140026B2D
0x140026454  mov     rax, cs:WPP_GLOBAL_Control
0x14002645b  cmp     [rax+48h], cx
0x14002645f  jz      loc_140026B2D
0x140026465  mov     [rsp+180h+var_138], edx
0x140026469  lea     rax, [rsp+180h+var_118]
0x14002646e  mov     [rsp+180h+var_140], r14
0x140026473  lea     r9d, [rcx+23h]
0x140026477  mov     [rsp+180h+var_148], rax
0x14002647c  mov     dword ptr [rsp+180h+var_150], 675h
0x140026484  call    WPP_RECORDER_SF_sDZZd
0x140026489  jmp     loc_140026B2D
0x14002648e  cmp     ebx, esi
0x140026490  jnz     short loc_1400264DA
0x140026492  lea     rdi, WPP_RECORDER_INITIALIZED
0x140026499  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400264a0  jz      loc_140026B2D
0x1400264a6  mov     rax, cs:WPP_GLOBAL_Control
0x1400264ad  cmp     [rax+48h], cx
0x1400264b1  jz      loc_140026B2D
0x1400264b7  mov     [rsp+180h+var_138], esi
0x1400264bb  lea     rax, [rsp+180h+var_118]
0x1400264c0  mov     [rsp+180h+var_140], r14
0x1400264c5  mov     r9d, 24h ; '$'
0x1400264cb  mov     [rsp+180h+var_148], rax
0x1400264d0  mov     dword ptr [rsp+180h+var_150], 681h
0x1400264d8  jmp     short loc_140026484
0x1400264da  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400264e1  jz      short loc_140026524
0x1400264e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400264ea  lea     rax, [rbp+80h+pusResult]
0x1400264ee  mov     [rsp+180h+var_140], rax
0x1400264f3  mov     r9d, 25h ; '%'
0x1400264f9  mov     dword ptr [rsp+180h+var_148], ebx
0x1400264fd  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140026504  mov     dword ptr [rsp+180h+var_150], 68Eh
0x14002650c  mov     r8d, r12d
0x14002650f  mov     rcx, [rcx+40h]
0x140026513  mov     dl, 3
0x140026515  mov     [rsp+180h+var_158], r13
0x14002651a  mov     qword ptr [rsp+180h+var_160], rax
0x14002651f  call    WPP_RECORDER_SF_sDdZ
0x140026524  mov     r9d, [rsp+180h+var_12C]
0x140026529  lea     rax, [rsp+180h+var_12F]
0x14002652e  mov     rcx, [rsp+180h+Instance]
0x140026533  lea     rdx, [rbp+80h+pusResult]
0x140026537  mov     [rsp+180h+var_150], rax
0x14002653c  mov     r8d, 29h ; ')'
0x140026542  lea     rax, [rsp+180h+Object]
0x140026547  mov     [rsp+180h+var_158], rax
0x14002654c  lea     rax, [rsp+180h+FileHandle]
0x140026551  mov     qword ptr [rsp+180h+var_160], rax; int
0x140026556  call    WcOpenPlaceHolder
0x14002655b  mov     ebx, eax
0x14002655d  xor     ecx, ecx
0x14002655f  mov     rax, [rsp+180h+FileHandle]
0x140026564  mov     [rsp+180h+FileHandle], rax
0x140026569  test    ebx, ebx
0x14002656b  jns     loc_140026646
0x140026571  cmp     ebx, 0C0000279h
0x140026577  jnz     short loc_1400265BF
0x140026579  mov     ebx, esi
0x14002657b  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140026582  jz      short loc_1400265B5
0x140026584  mov     rax, cs:WPP_GLOBAL_Control
0x14002658b  cmp     [rax+48h], cx
0x14002658f  jz      short loc_1400265B5
0x140026591  mov     [rsp+180h+var_138], esi
0x140026595  lea     rax, [rsp+180h+var_118]
0x14002659a  mov     [rsp+180h+var_140], r14
0x14002659f  lea     r9d, [rcx+26h]
0x1400265a3  mov     [rsp+180h+var_148], rax
0x1400265a8  mov     dword ptr [rsp+180h+var_150], 6B2h
0x1400265b0  call    WPP_RECORDER_SF_sDZZd
0x1400265b5  mov     r14, [rsp+180h+Object]
0x1400265ba  jmp     loc_140026B00
0x1400265bf  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400265c6  jz      short loc_1400265B5
0x1400265c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400265cf  lea     rax, [rbp+80h+pusResult]
0x1400265d3  mov     [rsp+180h+var_140], rax
0x1400265d8  mov     r9d, 27h ; '''
0x1400265de  mov     dword ptr [rsp+180h+var_148], ebx
0x1400265e2  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x1400265e9  mov     dword ptr [rsp+180h+var_150], 6C1h
0x1400265f1  mov     r8d, r12d
0x1400265f4  mov     rcx, [rcx+40h]
0x1400265f8  mov     dl, r15b
0x1400265fb  mov     [rsp+180h+var_158], r13
0x140026600  mov     qword ptr [rsp+180h+var_160], rax
0x140026605  call    WPP_RECORDER_SF_sDdZ
0x14002660a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140026611  jz      short loc_1400265B5
0x140026613  mov     rax, cs:WPP_GLOBAL_Control
0x14002661a  xor     edx, edx
0x14002661c  cmp     [rax+48h], dx
0x140026620  jz      short loc_1400265B5
0x140026622  mov     [rsp+180h+var_138], ebx
0x140026626  lea     rax, [rsp+180h+var_118]
0x14002662b  mov     [rsp+180h+var_140], r14
0x140026630  lea     r9d, [rdx+28h]
0x140026634  mov     [rsp+180h+var_148], rax
0x140026639  mov     dword ptr [rsp+180h+var_150], 6C2h
0x140026641  jmp     loc_1400265B0
0x140026646  mov     r14, [rsp+180h+Object]
0x14002664b  cmp     [rsp+180h+var_12F], cl
0x14002664f  jz      loc_140026A08
0x140026655  mov     rbx, [rsp+180h+Instance]
0x14002665a  mov     r8, r14
0x14002665d  mov     rdx, rbx
0x140026660  call    WcGetUnionContext
0x140026665  xor     edx, edx
0x140026667  mov     r13, rax
0x14002666a  test    rax, rax
0x14002666d  jnz     short loc_1400266D5
0x14002666f  xor     ebx, ebx
0x140026671  cmp     [rsp+180h+var_130], dl
0x140026675  jnz     loc_140026AA2
0x14002667b  mov     ebx, esi
0x14002667d  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140026684  jz      loc_140026B00
0x14002668a  mov     rcx, cs:WPP_GLOBAL_Control
0x140026691  lea     r9d, [rax+29h]
0x140026695  lea     rax, [rbp+80h+pusResult]
0x140026699  mov     r8d, r12d
0x14002669c  mov     [rsp+180h+var_140], rax
0x1400266a1  mov     dl, 3
0x1400266a3  mov     dword ptr [rsp+180h+var_148], esi
0x1400266a7  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x1400266ae  mov     rcx, [rcx+40h]
0x1400266b2  mov     dword ptr [rsp+180h+var_150], 6EBh
0x1400266ba  mov     [rsp+180h+var_158], rax
0x1400266bf  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x1400266c6  mov     qword ptr [rsp+180h+var_160], rax
0x1400266cb  call    WPP_RECORDER_SF_sDdZ
0x1400266d0  jmp     loc_140026B00
0x1400266d5  mov     eax, [rax+18h]
0x1400266d8  cmp     eax, 1
0x1400266db  jnz     loc_140026917
0x1400266e1  lea     rax, [rbp+80h+var_D0]
0x1400266e5  mov     esi, 1
0x1400266ea  mov     [rsp+180h+var_150], rax; __int64
0x1400266ef  mov     r9d, esi
0x1400266f2  lea     rax, [rbp+80h+Context]
0x1400266f6  mov     r8, r13
0x1400266f9  mov     rdx, r14; FileObject
0x1400266fc  mov     [rsp+180h+var_158], rax; __int64
0x140026701  mov     rcx, rbx; Instance
0x140026704  call    WcGetSetContextFileObject
0x140026709  xor     ecx, ecx
0x14002670b  mov     ebx, eax
0x14002670d  test    eax, eax
0x14002670f  js      loc_1400268AD
0x140026715  cmp     eax, 104h
0x14002671a  jz      loc_140026910
0x140026720  mov     r9, [rsp+180h+FileHandle]
0x140026725  lea     rax, [rsp+180h+var_118]
0x14002672a  mov     rdx, [rsp+180h+Instance]; FltObject
0x14002672f  mov     r8, r14; Object
0x140026732  mov     rcx, [rbp+80h+Data]; CallbackData
0x140026736  mov     [rsp+180h+var_158], rax; PUNICODE_STRING
0x14002673b  mov     al, [rsp+180h+var_130]
0x14002673f  mov     [rsp+180h+var_160], al; char
0x140026743  call    WcPartiallyExpandDirectory
0x140026748  xor     ecx, ecx
  ... truncated ...
```
