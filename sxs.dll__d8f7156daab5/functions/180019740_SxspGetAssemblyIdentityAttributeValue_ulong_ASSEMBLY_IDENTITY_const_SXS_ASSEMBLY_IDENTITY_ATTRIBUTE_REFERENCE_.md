# SxspGetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY const *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const * *,unsigned __int64 *)

- ea: `0x180019740`
- end: `0x180019cab`
- name: `?SxspGetAssemblyIdentityAttributeValue@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEAPEBGPEA_K@Z`
- size: `1387`
- prototype: `__int64 __fastcall(unsigned int, const struct _ASSEMBLY_IDENTITY *, const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *, const unsigned __int16 **, unsigned __int64 *)`
- caller_count: `20`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800143e0`
- `0x180015088`
- `0x180016870`
- `0x180017760`
- `0x180017dc0`
- `0x180023320`
- `0x180023ee0`
- `0x1800278b0`
- `0x18002f290`
- `0x180030950`
- `0x180040a30`
- `0x1800419e4`
- `0x1800434a0`
- `0x180054740`
- `0x180056eac`
- `0x18005a884`
- `0x180061ae0`
- `0x180061cb0`
- `0x180064f9c`
- `0x1800665f4`

## callees

- `0x18000a804`
- `0x180019740`
- `0x18001c2c8`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180019936`
- `ntdll!RtlPopFrame` at `0x180019936`
- `ntdll!_snprintf_s` at `0x180019896`
- `ntdll!_snprintf_s` at `0x180019896`
- `ntdll!RtlGetFrame` at `0x18001983a`
- `ntdll!RtlGetFrame` at `0x18001983a`
- `ntdll!RtlPushFrame` at `0x1800197d9`
- `ntdll!RtlPushFrame` at `0x1800197d9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800198b2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800198b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001985b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001985b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800198c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800198d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019a86`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800198c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800198d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019a86`

## pseudocode

```c
__int64 __fastcall SxspGetAssemblyIdentityAttributeValue(
        int a1,
        const struct _ASSEMBLY_IDENTITY *a2,
        unsigned __int16 **a3,
        const unsigned __int16 **a4,
        unsigned __int64 *a5)
{
  unsigned __int64 *v7; // r14
  const unsigned __int16 **v9; // r15
  const char *v10; // rcx
  const char *v11; // rsi
  const char *FrameName; // rbp
  int Previous; // edi
  PTEB_ACTIVE_FRAME v14; // rax
  PTEB_ACTIVE_FRAME v15; // rcx
  DWORD LastError; // ebx
  unsigned int v17; // ebx
  unsigned __int16 *v19; // rdx
  unsigned int v20; // r10d
  __int64 v21; // r9
  unsigned __int64 v22; // rsi
  unsigned __int64 v23; // rbp
  unsigned int v24; // r11d
  __int64 v25; // rax
  unsigned int v26; // ecx
  unsigned int v27; // r8d
  _QWORD *v28; // r13
  unsigned __int64 v29; // rbx
  unsigned __int16 *v30; // rdi
  unsigned __int64 v31; // rax
  unsigned __int16 *v32; // r9
  int v33; // ecx
  int v34; // eax
  int v35; // eax
  PCTEB_ACTIVE_FRAME_CONTEXT Context; // rdx
  unsigned __int64 v37; // rbx
  unsigned __int16 *v38; // rdx
  unsigned __int16 *v39; // r9
  unsigned __int64 v40; // rax
  unsigned __int64 v41; // rdi
  int v42; // eax
  int v43; // ecx
  __int64 v44; // rbx
  unsigned __int16 *v45; // rdx
  _QWORD *v46; // r11
  unsigned __int64 v47; // r9
  unsigned __int16 *v48; // r8
  unsigned __int64 v49; // rax
  unsigned __int64 v50; // r10
  int v51; // ecx
  int v52; // eax
  unsigned __int64 v53; // r10
  unsigned __int16 *v54; // rdx
  unsigned __int16 *v55; // r9
  unsigned __int64 v56; // rax
  unsigned __int64 v57; // r8
  int v58; // ecx
  int v59; // eax
  DWORD v60; // eax
  unsigned __int16 *v61; // [rsp+40h] [rbp-2A8h]
  __int64 v62; // [rsp+48h] [rbp-2A0h]
  unsigned __int16 *v63; // [rsp+50h] [rbp-298h]
  int v65; // [rsp+68h] [rbp-280h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+70h] [rbp-278h] BYREF
  __int64 v67; // [rsp+88h] [rbp-260h]
  int v68; // [rsp+90h] [rbp-258h]
  int *v69; // [rsp+98h] [rbp-250h]
  char Buffer[512]; // [rsp+A0h] [rbp-248h] BYREF

  Frame.Flags = 1;
  v7 = a5;
  Frame.Previous = 0;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006CDC0;
  v67 = 544438355;
  v9 = a4;
  v68 = 153;
  v69 = &v65;
  v65 = 0;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  if ( v9 )
    *v9 = 0;
  if ( a5 )
    *a5 = 0;
  if ( (a1 & 0xFFFFFFFE) != 0 )
  {
    v68 = 164;
    v11 = byte_18008517D;
    FrameName = byte_18008517D;
    Previous = 0;
    v14 = RtlGetFrame();
    if ( v14 && (v14->Flags & 1) != 0 )
    {
      v15 = v14;
    }
    else
    {
      v15 = 0;
      if ( !v14 )
      {
LABEL_10:
        LastError = GetLastError();
        _snprintf_s(
          Buffer,
          0x200u,
          0x1FFu,
          "%s(%d): Input parameter validation failed in function %s\n   Validation expression: %s\n",
          v11,
          Previous,
          FrameName,
          byte_18008517D);
        Buffer[511] = 0;
        OutputDebugStringA(Buffer);
        SetLastError(LastError);
LABEL_11:
        SetLastError(0x57u);
        *v69 = 0;
        goto LABEL_12;
      }
    }
    Context = v14->Context;
    if ( Context )
    {
      if ( Context->FrameName )
        FrameName = Context->FrameName;
      if ( (Context->Flags & 1) != 0 && *(_QWORD *)&Context[1].Flags )
        v11 = *(const char **)&Context[1].Flags;
    }
    if ( v15 && *(_QWORD *)&v15[1].Flags == 544438355 && LODWORD(v15[1].Previous) )
      Previous = (int)v15[1].Previous;
    goto LABEL_10;
  }
  if ( !a2 )
  {
    v68 = 165;
    FusionpTraceParameterCheck(v10);
    goto LABEL_11;
  }
  if ( !a3 )
  {
    v68 = 166;
    FusionpTraceParameterCheck(v10);
    goto LABEL_11;
  }
  v19 = *a3;
  v20 = 0;
  v21 = *((_QWORD *)a2 + 5);
  v22 = (unsigned __int64)a3[1];
  v23 = (unsigned __int64)a3[3];
  v24 = *((_DWORD *)a2 + 4);
  v61 = *a3;
  v63 = a3[2];
  v62 = v21;
  while ( 2 )
  {
    if ( v20 < v24 )
    {
      v25 = v20;
      v26 = (v24 + v20) >> 1;
      if ( v26 != v24 )
        v25 = v26;
      v27 = v25;
      v28 = *(_QWORD **)(v21 + 8 * v25);
      v29 = v28[1];
      v30 = (unsigned __int16 *)v28[4];
      v31 = v29;
      if ( v22 <= v29 )
        v31 = v22;
      v32 = &v19[v31];
      while ( v19 < v32 )
      {
        v33 = *v30++;
        v34 = *v19++;
        v35 = v34 - v33;
        if ( v35 )
          goto LABEL_29;
      }
      if ( v22 != v29 )
      {
        if ( v22 >= v29 )
        {
LABEL_28:
          v35 = -1;
          goto LABEL_29;
        }
        v35 = 1;
LABEL_29:
        if ( v35 < 0 )
        {
          if ( v24 == v27 )
            break;
          v19 = v61;
          v24 = v27;
          v21 = v62;
        }
        else
        {
          if ( v20 == v27 )
            break;
          v19 = v61;
          v20 = v27;
          v21 = v62;
        }
        continue;
      }
      v37 = v28[2];
      v38 = v63;
      v39 = (unsigned __int16 *)v28[5];
      v40 = v37;
      if ( v23 <= v37 )
        v40 = v23;
      v41 = (unsigned __int64)&v63[v40];
      while ( (unsigned __int64)v38 < v41 )
      {
        v42 = *v38++;
        v43 = *v39++;
        v35 = v42 - v43;
        if ( v35 )
          goto LABEL_29;
      }
      if ( v23 < v37 )
      {
        v35 = 1;
        goto LABEL_29;
      }
      if ( v23 != v37 )
        goto LABEL_28;
      if ( v28 )
      {
        if ( !v27 )
          goto LABEL_48;
        do
        {
          v44 = v27 - 1;
          v45 = v61;
          v46 = *(_QWORD **)(v62 + 8 * v44);
          v47 = v46[1];
          v48 = (unsigned __int16 *)v46[4];
          v49 = v47;
          if ( v22 <= v47 )
            v49 = v22;
          v50 = (unsigned __int64)&v61[v49];
          while ( (unsigned __int64)v45 < v50 )
          {
            v51 = *v45++;
            v52 = *v48++;
            if ( v51 != v52 )
              goto LABEL_47;
          }
          if ( v22 != v47 )
            break;
          v53 = v46[2];
          v54 = v63;
          v55 = (unsigned __int16 *)v46[5];
          v56 = v53;
          if ( v23 <= v53 )
            v56 = v23;
          v57 = (unsigned __int64)&v63[v56];
          while ( (unsigned __int64)v54 < v57 )
          {
            v58 = *v54++;
            v59 = *v55++;
            if ( v58 != v59 )
              goto LABEL_47;
          }
          if ( v23 != v53 )
            break;
          v27 = v44;
          v28 = *(_QWORD **)(v62 + 8 * v44);
        }
        while ( (_DWORD)v44 );
LABEL_47:
        v7 = a5;
        v9 = a4;
        if ( v28 )
        {
LABEL_48:
          if ( v9 )
            *v9 = (const unsigned __int16 *)v28[6];
          if ( v7 )
            *v7 = v28[3];
          goto LABEL_52;
        }
      }
    }
    break;
  }
  if ( (a1 & 1) != 0 )
  {
LABEL_52:
    v65 = 1;
  }
  else
  {
    SetLastError(0x490u);
    *v69 = 0;
    FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_18006D3E0);
  }
LABEL_12:
  v17 = v65;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v69 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v60 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v60, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v17;
}

```

## disassembly

```asm
0x180019740  mov     r11, rsp
0x180019743  push    rbx
0x180019744  sub     rsp, 2E0h
0x18001974b  mov     rax, cs:__security_cookie
0x180019752  xor     rax, rsp
0x180019755  mov     [rsp+2E8h+var_48], rax
0x18001975d  mov     [r11-18h], rdi
0x180019761  lea     rax, qword_18006CDC0
0x180019768  mov     [r11-20h], r12
0x18001976c  mov     rbx, r8
0x18001976f  mov     [r11-28h], r13
0x180019773  mov     r12d, ecx
0x180019776  mov     [rsp+2E8h+Frame.Flags], 1
0x18001977e  lea     rcx, [rsp+2E8h+Frame]; Frame
0x180019783  mov     [r11-30h], r14
0x180019787  xor     r13d, r13d
0x18001978a  mov     r14, [rsp+2E8h+arg_20]
0x180019792  mov     rdi, rdx
0x180019795  mov     [rsp+2E8h+Frame.Previous], r13
0x18001979a  mov     [r11-268h], rax
0x1800197a1  lea     rax, [rsp+2E8h+var_280]
0x1800197a6  mov     qword ptr [r11-260h], 20737853h
0x1800197b1  mov     [r11-38h], r15
0x1800197b5  mov     r15, r9
0x1800197b8  mov     [rsp+2E8h+var_258], 99h
0x1800197c3  mov     [r11-250h], rax
0x1800197ca  mov     [rsp+2E8h+var_288], r9
0x1800197cf  mov     [rsp+2E8h+var_290], r14
0x1800197d4  mov     [rsp+2E8h+var_280], r13d
0x1800197d9  call    cs:__imp_RtlPushFrame
0x1800197e0  nop     dword ptr [rax+rax+00h]
0x1800197e5  cmp     cs:g_FusionEnterExitTracingEnabled, r13b
0x1800197ec  jnz     loc_180019B01
0x1800197f2  test    r15, r15
0x1800197f5  jz      short loc_1800197FA
0x1800197f7  mov     [r15], r13
0x1800197fa  test    r14, r14
0x1800197fd  jz      short loc_180019802
0x1800197ff  mov     [r14], r13
0x180019802  mov     [rsp+2E8h+arg_0], rbp
0x18001980a  mov     [rsp+2E8h+var_10], rsi
0x180019812  test    r12d, 0FFFFFFFEh
0x180019819  jz      loc_18001995E
0x18001981f  lea     r14, byte_18008517D
0x180019826  mov     [rsp+2E8h+var_258], 0A4h
0x180019831  mov     rsi, r14
0x180019834  mov     rbp, r14
0x180019837  mov     edi, r13d
0x18001983a  call    cs:__imp_RtlGetFrame
0x180019841  nop     dword ptr [rax+rax+00h]
0x180019846  test    rax, rax
0x180019849  jnz     loc_180019A20
0x18001984f  mov     rcx, r13
0x180019852  test    rax, rax
0x180019855  jnz     loc_180019A2C
0x18001985b  call    cs:__imp_GetLastError
0x180019862  nop     dword ptr [rax+rax+00h]
0x180019867  mov     [rsp+2E8h+var_2B0], r14
0x18001986c  lea     r9, aSDInputParamet; "%s(%d): Input parameter validation fail"...
0x180019873  mov     [rsp+2E8h+var_2B8], rbp
0x180019878  lea     rcx, [rsp+2E8h+Buffer]; Buffer
0x180019880  mov     [rsp+2E8h+var_2C0], edi
0x180019884  mov     edx, 200h; BufferCount
0x180019889  mov     r8d, 1FFh; MaxCount
0x18001988f  mov     [rsp+2E8h+var_2C8], rsi
0x180019894  mov     ebx, eax
0x180019896  call    cs:__imp__snprintf_s
0x18001989d  nop     dword ptr [rax+rax+00h]
0x1800198a2  lea     rcx, [rsp+2E8h+Buffer]; lpOutputString
0x1800198aa  mov     [rsp+2E8h+var_49], r13b
0x1800198b2  call    cs:__imp_OutputDebugStringA
0x1800198b9  nop     dword ptr [rax+rax+00h]
0x1800198be  mov     ecx, ebx; dwErrCode
0x1800198c0  call    cs:__imp_SetLastError
0x1800198c7  nop     dword ptr [rax+rax+00h]
0x1800198cc  mov     ecx, 57h ; 'W'; dwErrCode
0x1800198d1  call    cs:__imp_SetLastError
0x1800198d8  nop     dword ptr [rax+rax+00h]
0x1800198dd  mov     rax, [rsp+2E8h+var_250]
0x1800198e5  mov     [rax], r13d
0x1800198e8  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x1800198ef  mov     ebx, [rsp+2E8h+var_280]
0x1800198f3  mov     r15, [rsp+2E8h+var_38]
0x1800198fb  mov     r14, [rsp+2E8h+var_30]
0x180019903  mov     r13, [rsp+2E8h+var_28]
0x18001990b  mov     r12, [rsp+2E8h+var_20]
0x180019913  mov     rdi, [rsp+2E8h+var_18]
0x18001991b  mov     rsi, [rsp+2E8h+var_10]
0x180019923  mov     rbp, [rsp+2E8h+arg_0]
0x18001992b  jnz     loc_180019C78
0x180019931  lea     rcx, [rsp+2E8h+Frame]; Frame
0x180019936  call    cs:__imp_RtlPopFrame
0x18001993d  nop     dword ptr [rax+rax+00h]
0x180019942  mov     eax, ebx
0x180019944  mov     rcx, [rsp+2E8h+var_48]
0x18001994c  xor     rcx, rsp; StackCookie
0x18001994f  call    __security_check_cookie
0x180019954  add     rsp, 2E0h
0x18001995b  pop     rbx
0x18001995c  retn
0x18001995e  test    rdi, rdi
0x180019961  jz      loc_180019C1D
0x180019967  test    rbx, rbx
0x18001996a  jz      loc_180019C32
0x180019970  mov     rdx, [rbx]
0x180019973  mov     r10d, r13d
0x180019976  mov     rax, [rbx+10h]
0x18001997a  mov     r9, [rdi+28h]
0x18001997e  mov     rsi, [rbx+8]
0x180019982  mov     rbp, [rbx+18h]
0x180019986  mov     r11d, [rdi+10h]
0x18001998a  mov     [rsp+2E8h+var_2A8], rdx
0x18001998f  mov     [rsp+2E8h+var_298], rax
0x180019994  mov     [rsp+2E8h+var_2A0], r9
0x180019999  cmp     r10d, r11d
0x18001999c  jnb     loc_180019A7B
0x1800199a2  mov     eax, r10d
0x1800199a5  lea     ecx, [r11+r10]
0x1800199a9  shr     ecx, 1
0x1800199ab  cmp     ecx, r11d
0x1800199ae  cmovnz  eax, ecx
0x1800199b1  mov     r8d, eax
0x1800199b4  mov     r13, [r9+rax*8]
0x1800199b8  mov     rbx, [r13+8]
0x1800199bc  mov     rdi, [r13+20h]
0x1800199c0  cmp     rsi, rbx
0x1800199c3  mov     rax, rbx
0x1800199c6  cmovbe  rax, rsi
0x1800199ca  lea     r9, [rdx+rax*2]
0x1800199ce  cmp     rdx, r9
0x1800199d1  jnb     short loc_1800199E7
0x1800199d3  movzx   ecx, word ptr [rdi]
0x1800199d6  add     rdi, 2
0x1800199da  movzx   eax, word ptr [rdx]
0x1800199dd  add     rdx, 2
0x1800199e1  sub     eax, ecx
0x1800199e3  jz      short loc_1800199CE
0x1800199e5  jmp     short loc_1800199FB
0x1800199e7  cmp     rsi, rbx
0x1800199ea  jz      loc_180019B0B
0x1800199f0  jb      loc_180019C47
0x1800199f6  mov     eax, 0FFFFFFFFh
0x1800199fb  test    eax, eax
0x1800199fd  js      loc_180019C02
0x180019a03  jz      loc_180019B52
0x180019a09  cmp     r10d, r8d
0x180019a0c  jz      short loc_180019A7B
0x180019a0e  mov     rdx, [rsp+2E8h+var_2A8]
0x180019a13  mov     r10d, r8d
0x180019a16  mov     r9, [rsp+2E8h+var_2A0]
0x180019a1b  jmp     loc_180019999
0x180019a20  test    byte ptr [rax], 1
0x180019a23  jz      loc_18001984F
0x180019a29  mov     rcx, rax
0x180019a2c  mov     rdx, [rax+10h]
0x180019a30  test    rdx, rdx
0x180019a33  jz      short loc_180019A52
0x180019a35  mov     rax, [rdx+8]
0x180019a39  test    rax, rax
0x180019a3c  jz      short loc_180019A41
0x180019a3e  mov     rbp, rax
0x180019a41  test    byte ptr [rdx], 1
0x180019a44  jz      short loc_180019A52
0x180019a46  mov     rax, [rdx+10h]
0x180019a4a  test    rax, rax
0x180019a4d  jz      short loc_180019A52
0x180019a4f  mov     rsi, rax
0x180019a52  test    rcx, rcx
0x180019a55  jz      loc_18001985B
0x180019a5b  cmp     qword ptr [rcx+18h], 20737853h
0x180019a63  jnz     loc_18001985B
0x180019a69  mov     eax, [rcx+20h]
0x180019a6c  test    eax, eax
0x180019a6e  jz      loc_18001985B
0x180019a74  mov     edi, eax
0x180019a76  jmp     loc_18001985B
0x180019a7b  test    r12b, 1
0x180019a7f  jnz     short loc_180019AF4
0x180019a81  mov     ecx, 490h; dwErrCode
0x180019a86  call    cs:__imp_SetLastError
0x180019a8d  nop     dword ptr [rax+rax+00h]
0x180019a92  mov     rax, [rsp+2E8h+var_250]
0x180019a9a  lea     rcx, off_18006D3E0; struct _CALL_SITE_INFO *
0x180019aa1  mov     dword ptr [rax], 0
0x180019aa7  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x180019aac  jmp     loc_1800198E8
0x180019ab1  cmp     rsi, r9
0x180019ab4  jz      loc_180019BB5
0x180019aba  jb      loc_180019C5B
0x180019ac0  mov     ecx, 0FFFFFFFFh
0x180019ac5  test    ecx, ecx
0x180019ac7  jz      loc_180019C65
0x180019acd  mov     r14, [rsp+2E8h+var_290]
0x180019ad2  mov     r15, [rsp+2E8h+var_288]
0x180019ad7  test    r13, r13
0x180019ada  jz      short loc_180019A7B
0x180019adc  test    r15, r15
0x180019adf  jz      short loc_180019AE8
0x180019ae1  mov     rax, [r13+30h]
0x180019ae5  mov     [r15], rax
0x180019ae8  test    r14, r14
0x180019aeb  jz      short loc_180019AF4
0x180019aed  mov     rax, [r13+18h]
0x180019af1  mov     [r14], rax
0x180019af4  mov     [rsp+2E8h+var_280], 1
0x180019afc  jmp     loc_1800198E8
0x180019b01  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180019b06  jmp     loc_1800197F2
0x180019b0b  mov     rbx, [r13+10h]
0x180019b0f  mov     rdx, [rsp+2E8h+var_298]
0x180019b14  cmp     rbp, rbx
0x180019b17  mov     r9, [r13+28h]
0x180019b1b  mov     rax, rbx
0x180019b1e  cmovbe  rax, rbp
0x180019b22  lea     rdi, [rdx+rax*2]
0x180019b26  cmp     rdx, rdi
0x180019b29  jnb     short loc_180019B43
0x180019b2b  movzx   eax, word ptr [rdx]
0x180019b2e  add     rdx, 2
0x180019b32  movzx   ecx, word ptr [r9]
0x180019b36  add     r9, 2
0x180019b3a  sub     eax, ecx
0x180019b3c  jz      short loc_180019B26
0x180019b3e  jmp     loc_1800199FB
0x180019b43  cmp     rbp, rbx
0x180019b46  jb      loc_180019C51
0x180019b4c  jnz     loc_1800199F6
0x180019b52  test    r13, r13
0x180019b55  jz      loc_180019A7B
0x180019b5b  test    r8d, r8d
0x180019b5e  jz      loc_180019ADC
0x180019b64  mov     rdi, [rsp+2E8h+var_2A8]
0x180019b69  mov     r14, [rsp+2E8h+var_2A0]
0x180019b6e  mov     r15, [rsp+2E8h+var_298]
0x180019b73  lea     ebx, [r8-1]
0x180019b77  mov     rdx, rdi
0x180019b7a  mov     r11, [r14+rbx*8]
0x180019b7e  mov     r9, [r11+8]
0x180019b82  mov     r8, [r11+20h]
0x180019b86  cmp     rsi, r9
0x180019b89  mov     rax, r9
0x180019b8c  cmovbe  rax, rsi
0x180019b90  lea     r10, [rdi+rax*2]
0x180019b94  cmp     rdx, r10
0x180019b97  jnb     loc_180019AB1
0x180019b9d  movzx   ecx, word ptr [rdx]
0x180019ba0  add     rdx, 2
0x180019ba4  movzx   eax, word ptr [r8]
0x180019ba8  add     r8, 2
0x180019bac  sub     ecx, eax
0x180019bae  jz      short loc_180019B94
0x180019bb0  jmp     loc_180019AC5
0x180019bb5  mov     r10, [r11+10h]
0x180019bb9  mov     rdx, r15
0x180019bbc  mov     r9, [r11+28h]
0x180019bc0  cmp     rbp, r10
0x180019bc3  mov     rax, r10
0x180019bc6  cmovbe  rax, rbp
0x180019bca  lea     r8, [r15+rax*2]
0x180019bce  xchg    ax, ax
0x180019bd0  cmp     rdx, r8
0x180019bd3  jnb     short loc_180019BED
0x180019bd5  movzx   ecx, word ptr [rdx]
0x180019bd8  add     rdx, 2
0x180019bdc  movzx   eax, word ptr [r9]
0x180019be0  add     r9, 2
0x180019be4  sub     ecx, eax
0x180019be6  jz      short loc_180019BD0
0x180019be8  jmp     loc_180019AC5
0x180019bed  cmp     rbp, r10
0x180019bf0  jz      short loc_180019C65
0x180019bf2  jnb     loc_180019AC0
0x180019bf8  mov     ecx, 1
0x180019bfd  jmp     loc_180019AC5
0x180019c02  cmp     r11d, r8d
0x180019c05  jz      loc_180019A7B
0x180019c0b  mov     rdx, [rsp+2E8h+var_2A8]
0x180019c10  mov     r11d, r8d
0x180019c13  mov     r9, [rsp+2E8h+var_2A0]
0x180019c18  jmp     loc_180019999
0x180019c1d  mov     [rsp+2E8h+var_258], 0A5h
0x180019c28  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180019c2d  jmp     loc_1800198CC
0x180019c32  mov     [rsp+2E8h+var_258], 0A6h
0x180019c3d  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180019c42  jmp     loc_1800198CC
0x180019c47  mov     eax, 1
0x180019c4c  jmp     loc_1800199FB
0x180019c51  mov     eax, 1
0x180019c56  jmp     loc_1800199FB
0x180019c5b  mov     ecx, 1
0x180019c60  jmp     loc_180019AC5
0x180019c65  mov     r8d, ebx
0x180019c68  mov     r13, r11
0x180019c6b  test    ebx, ebx
0x180019c6d  jnz     loc_180019B73
0x180019c73  jmp     loc_180019ACD
0x180019c78  mov     rax, [rsp+2E8h+var_250]
0x180019c80  cmp     dword ptr [rax], 0
0x180019c83  jz      short loc_180019C91
  ... truncated ...
```
