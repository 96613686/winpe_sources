# CRdpDrUtil::MapPrintDriverName(ushort const *,ushort const *,ushort const *,ulong,ulong,ushort *,ulong,ulong *)

- ea: `0x180019224`
- end: `0x1800193d9`
- name: `?MapPrintDriverName@CRdpDrUtil@@QEAAHPEBG00KKPEAGKPEAK@Z`
- size: `437`
- prototype: `int(CRdpDrUtil *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800166e4`

## callees

- `0x18000d270`
- `0x180019224`
- `0x1800197e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019395`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800192f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800192f7`
- `ext-ms-win-setupapi-inf-l1-1-0!SetupFindFirstLineW` at `0x1800192a7`
- `ext-ms-win-setupapi-inf-l1-1-0!SetupFindFirstLineW` at `0x1800192a7`
- `ext-ms-win-setupapi-inf-l1-1-0!SetupCloseInfFile` at `0x18001938b`
- `ext-ms-win-setupapi-inf-l1-1-0!SetupCloseInfFile` at `0x18001938b`
- `ext-ms-win-setupapi-inf-l1-1-0!SetupOpenInfFileW` at `0x180019275`
- `ext-ms-win-setupapi-inf-l1-1-0!SetupOpenInfFileW` at `0x180019275`
- `ext-ms-win-setupapi-inf-l1-1-0!SetupFindNextLine` at `0x18001933c`
- `ext-ms-win-setupapi-inf-l1-1-0!SetupFindNextLine` at `0x18001933c`
- `ext-ms-win-setupapi-inf-l1-1-1!SetupGetStringFieldW` at `0x1800192e2`
- `ext-ms-win-setupapi-inf-l1-1-1!SetupGetStringFieldW` at `0x180019360`
- `ext-ms-win-setupapi-inf-l1-1-1!SetupGetStringFieldW` at `0x18001937a`
- `ext-ms-win-setupapi-inf-l1-1-1!SetupGetStringFieldW` at `0x1800192e2`
- `ext-ms-win-setupapi-inf-l1-1-1!SetupGetStringFieldW` at `0x180019360`
- `ext-ms-win-setupapi-inf-l1-1-1!SetupGetStringFieldW` at `0x18001937a`

## pseudocode

```c
__int64 __fastcall CRdpDrUtil::MapPrintDriverName(
        CRdpDrUtil *this,
        const unsigned __int16 *a2,
        WCHAR *a3,
        const unsigned __int16 *a4,
        DWORD FieldIndex,
        DWORD a6,
        unsigned __int16 *ReturnBuffer,
        DWORD ReturnBufferSize,
        PDWORD a9)
{
  HINF v12; // rax
  DWORD *RequiredSize; // r13
  unsigned int v14; // ebx
  void *v15; // r15
  int v16; // esi
  BOOL StringFieldW; // edi
  unsigned __int16 *v18; // rax
  int v19; // ecx
  int v20; // edx
  _INFCONTEXT Context; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v22; // [rsp+80h] [rbp+30h] BYREF
  const unsigned __int16 *v23; // [rsp+88h] [rbp+38h]

  v23 = a2;
  v22 = (unsigned __int16 *)this;
  memset(&Context, 0, sizeof(Context));
  if ( !(unsigned __int8)IsSetupOpenInfFileWPresent() )
    return 0;
  v12 = SetupOpenInfFileW(a3, 0, 3u, 0);
  RequiredSize = a9;
  v14 = 1;
  v15 = v12;
  if ( v12 == (HINF)-1LL )
  {
    GetLastError();
    v16 = 1;
    goto LABEL_12;
  }
  memset(&Context, 0, sizeof(Context));
  if ( !SetupFindFirstLineW(v12, a4, 0, &Context) )
  {
    v16 = 1;
    if ( GetLastError() == -536870654 )
    {
      StringFieldW = 1;
      goto LABEL_13;
    }
    GetLastError();
LABEL_12:
    StringFieldW = 0;
    goto LABEL_13;
  }
  v16 = 0;
  StringFieldW = SetupGetStringFieldW(&Context, FieldIndex, ReturnBuffer, ReturnBufferSize, RequiredSize);
  if ( StringFieldW && !ReturnBuffer )
  {
    SetLastError(0x7Au);
    goto LABEL_12;
  }
LABEL_13:
  while ( StringFieldW && !v16 )
  {
    v18 = ReturnBuffer;
    do
    {
      v19 = *(unsigned __int16 *)((char *)v18 + (char *)v23 - (char *)ReturnBuffer);
      v20 = *v18 - v19;
      if ( v20 )
        break;
      ++v18;
    }
    while ( v19 );
    if ( !v20 )
    {
      StringFieldW = SetupGetStringFieldW(&Context, a6, ReturnBuffer, ReturnBufferSize, RequiredSize);
      break;
    }
    if ( SetupFindNextLine(&Context, &Context) )
    {
      v16 = 0;
      StringFieldW = SetupGetStringFieldW(&Context, FieldIndex, ReturnBuffer, ReturnBufferSize, RequiredSize);
    }
    else
    {
      v16 = 1;
    }
  }
  if ( v15 != (void *)-1LL )
    SetupCloseInfFile(v15);
  if ( !StringFieldW )
  {
    if ( GetLastError() != 122 )
    {
      v22 = a3;
      TsLogError(&EVENT_NOTIFY_ERRORPARSINGINF, 1u, &v22);
    }
    return 0;
  }
  if ( v16 )
    return 0;
  return v14;
}

```

## disassembly

```asm
0x180019224  mov     rax, rsp
0x180019227  mov     [rax+18h], rbx
0x18001922b  mov     [rax+20h], rsi
0x18001922f  mov     [rax+10h], rdx
0x180019233  mov     [rax+8], rcx
0x180019237  push    rbp
0x180019238  push    rdi
0x180019239  push    r12
0x18001923b  push    r13
0x18001923d  push    r15
0x18001923f  mov     rbp, rsp
0x180019242  sub     rsp, 50h
0x180019246  xorps   xmm0, xmm0
0x180019249  xor     eax, eax
0x18001924b  movups  xmmword ptr [rbp+Context.Inf], xmm0
0x18001924f  mov     qword ptr [rbp+Context.Section], rax
0x180019253  mov     rdi, r9
0x180019256  mov     r12, r8
0x180019259  call    IsSetupOpenInfFileWPresent
0x18001925e  test    al, al
0x180019260  jnz     short loc_180019269
0x180019262  xor     eax, eax
0x180019264  jmp     loc_1800193C0
0x180019269  xor     r9d, r9d; ErrorLine
0x18001926c  xor     edx, edx; InfClass
0x18001926e  mov     rcx, r12; FileName
0x180019271  lea     r8d, [r9+3]; InfStyle
0x180019275  call    cs:__imp_SetupOpenInfFileW
0x18001927b  mov     r13, [rbp+arg_40]
0x18001927f  mov     ebx, 1
0x180019284  mov     r15, rax
0x180019287  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001928b  jz      short loc_1800192FF
0x18001928d  xorps   xmm0, xmm0
0x180019290  lea     r9, [rbp+Context]; Context
0x180019294  xor     eax, eax
0x180019296  xor     r8d, r8d; Key
0x180019299  mov     rdx, rdi; Section
0x18001929c  mov     qword ptr [rbp+Context.Section], rax
0x1800192a0  mov     rcx, r15; InfHandle
0x1800192a3  movups  xmmword ptr [rbp+Context.Inf], xmm0
0x1800192a7  call    cs:__imp_SetupFindFirstLineW
0x1800192ad  test    eax, eax
0x1800192af  jnz     short loc_1800192CC
0x1800192b1  mov     esi, ebx
0x1800192b3  call    cs:__imp_GetLastError
0x1800192b9  cmp     eax, 0E0000102h
0x1800192be  jz      short loc_1800192C8
0x1800192c0  call    cs:__imp_GetLastError
0x1800192c6  jmp     short loc_180019307
0x1800192c8  mov     edi, ebx
0x1800192ca  jmp     short loc_180019309
0x1800192cc  mov     r9d, [rbp+ReturnBufferSize]; ReturnBufferSize
0x1800192d0  lea     rcx, [rbp+Context]; Context
0x1800192d4  mov     r8, [rbp+ReturnBuffer]; ReturnBuffer
0x1800192d8  xor     esi, esi
0x1800192da  mov     edx, [rbp+FieldIndex]; FieldIndex
0x1800192dd  mov     [rsp+50h+RequiredSize], r13; RequiredSize
0x1800192e2  call    cs:__imp_SetupGetStringFieldW
0x1800192e8  mov     edi, eax
0x1800192ea  test    eax, eax
0x1800192ec  jz      short loc_180019309
0x1800192ee  cmp     [rbp+ReturnBuffer], rsi
0x1800192f2  jnz     short loc_180019309
0x1800192f4  lea     ecx, [rsi+7Ah]; dwErrCode
0x1800192f7  call    cs:__imp_SetLastError
0x1800192fd  jmp     short loc_180019307
0x1800192ff  call    cs:__imp_GetLastError
0x180019305  mov     esi, ebx
0x180019307  xor     edi, edi
0x180019309  test    edi, edi
0x18001930b  jz      short loc_180019382
0x18001930d  test    esi, esi
0x18001930f  jnz     short loc_180019382
0x180019311  mov     rax, [rbp+ReturnBuffer]
0x180019315  mov     r8, [rbp+arg_8]
0x180019319  sub     r8, rax
0x18001931c  movzx   edx, word ptr [rax]
0x18001931f  movzx   ecx, word ptr [rax+r8]
0x180019324  sub     edx, ecx
0x180019326  jnz     short loc_180019330
0x180019328  add     rax, 2
0x18001932c  test    ecx, ecx
0x18001932e  jnz     short loc_18001931C
0x180019330  lea     rcx, [rbp+Context]; Context
0x180019334  test    edx, edx
0x180019336  jz      short loc_18001936A
0x180019338  lea     rdx, [rbp+Context]; ContextOut
0x18001933c  call    cs:__imp_SetupFindNextLine
0x180019342  test    eax, eax
0x180019344  jnz     short loc_18001934A
0x180019346  mov     esi, ebx
0x180019348  jmp     short loc_180019309
0x18001934a  mov     r9d, [rbp+ReturnBufferSize]; ReturnBufferSize
0x18001934e  lea     rcx, [rbp+Context]; Context
0x180019352  mov     r8, [rbp+ReturnBuffer]; ReturnBuffer
0x180019356  xor     esi, esi
0x180019358  mov     edx, [rbp+FieldIndex]; FieldIndex
0x18001935b  mov     [rsp+50h+RequiredSize], r13; RequiredSize
0x180019360  call    cs:__imp_SetupGetStringFieldW
0x180019366  mov     edi, eax
0x180019368  jmp     short loc_180019309
0x18001936a  mov     r9d, [rbp+ReturnBufferSize]; ReturnBufferSize
0x18001936e  mov     r8, [rbp+ReturnBuffer]; ReturnBuffer
0x180019372  mov     edx, [rbp+arg_28]; FieldIndex
0x180019375  mov     [rsp+50h+RequiredSize], r13; RequiredSize
0x18001937a  call    cs:__imp_SetupGetStringFieldW
0x180019380  mov     edi, eax
0x180019382  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180019386  jz      short loc_180019391
0x180019388  mov     rcx, r15; InfHandle
0x18001938b  call    cs:__imp_SetupCloseInfFile
0x180019391  test    edi, edi
0x180019393  jnz     short loc_1800193B8
0x180019395  call    cs:__imp_GetLastError
0x18001939b  cmp     eax, 7Ah ; 'z'
0x18001939e  jz      short loc_1800193BC
0x1800193a0  lea     r8, [rbp+arg_0]; unsigned __int16 **
0x1800193a4  mov     [rbp+arg_0], r12
0x1800193a8  mov     edx, ebx; int
0x1800193aa  lea     rcx, EVENT_NOTIFY_ERRORPARSINGINF; struct _EVENT_DESCRIPTOR *
0x1800193b1  call    ?TsLogError@@YAXAEBU_EVENT_DESCRIPTOR@@HQEAPEAGK@Z; TsLogError(_EVENT_DESCRIPTOR const &,int,ushort * * const,ulong)
0x1800193b6  jmp     short loc_1800193BC
0x1800193b8  test    esi, esi
0x1800193ba  jz      short loc_1800193BE
0x1800193bc  xor     ebx, ebx
0x1800193be  mov     eax, ebx
0x1800193c0  lea     r11, [rsp+50h+var_s0]
0x1800193c5  mov     rbx, [r11+40h]
0x1800193c9  mov     rsi, [r11+48h]
0x1800193cd  mov     rsp, r11
0x1800193d0  pop     r15
0x1800193d2  pop     r13
0x1800193d4  pop     r12
0x1800193d6  pop     rdi
0x1800193d7  pop     rbp
0x1800193d8  retn
```
