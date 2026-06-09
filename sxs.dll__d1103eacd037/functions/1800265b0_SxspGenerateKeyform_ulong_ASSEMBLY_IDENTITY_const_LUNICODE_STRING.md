# SxspGenerateKeyform(ulong,_ASSEMBLY_IDENTITY const *,_LUNICODE_STRING *)

- ea: `0x1800265b0`
- end: `0x180026a50`
- name: `?SxspGenerateKeyform@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEAU_LUNICODE_STRING@@@Z`
- size: `1184`
- prototype: `__int64 __fastcall(unsigned int, const struct _ASSEMBLY_IDENTITY *, struct _LUNICODE_STRING *)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180023ee0`
- `0x180025e00`
- `0x18002bdb4`
- `0x180030950`

## callees

- `0x18000a804`
- `0x18001c2c8`
- `0x180022f60`
- `0x1800265b0`
- `0x1800527e0`
- `0x18005d2b0`
- `0x18005d2e4`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180026786`
- `ntdll!RtlCompareUnicodeString` at `0x180026786`
- `ntdll!RtlPopFrame` at `0x180026893`
- `ntdll!RtlPopFrame` at `0x180026893`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800269ef`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800269ef`
- `ntdll!RtlPushFrame` at `0x18002661f`
- `ntdll!RtlPushFrame` at `0x18002661f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026a36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026a36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026823`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002694c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026974`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800269a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800269fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026823`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002694c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026974`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800269a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800269fd`
- `ServicingCommon!CreateKeyformFromAttributesIntoBuffer` at `0x180026805`
- `ServicingCommon!CreateKeyformFromAttributesIntoBuffer` at `0x180026805`

## pseudocode

```c
__int64 __fastcall SxspGenerateKeyform(int a1, const struct _ASSEMBLY_IDENTITY *a2, struct _LUNICODE_STRING *a3)
{
  const char *v6; // rcx
  __int64 v7; // rax
  unsigned __int64 v8; // rbx
  char *v9; // rdi
  void *Elements; // rax
  const char *v11; // rcx
  __int64 v12; // rax
  const char *v13; // rcx
  unsigned int v14; // r14d
  unsigned __int64 v15; // rsi
  __int64 v16; // r12
  __int64 v17; // r9
  __int64 v18; // r14
  _QWORD *v19; // r15
  char **v20; // rdx
  char *v21; // r8
  char *v22; // rcx
  char *v23; // r13
  __int64 v24; // rax
  WCHAR *v25; // rdx
  __int64 v26; // rax
  wchar_t *v27; // rax
  __int64 v28; // rax
  NTSTATUS v29; // eax
  unsigned int v30; // ebx
  void *v31; // rcx
  __int64 v33; // rax
  __int64 v34; // rax
  DWORD v35; // eax
  DWORD LastError; // eax
  __int64 v37; // [rsp+28h] [rbp-69h]
  char *v38; // [rsp+28h] [rbp-69h]
  unsigned int v39; // [rsp+30h] [rbp-61h]
  __int64 v40; // [rsp+38h] [rbp-59h]
  UNICODE_STRING String2; // [rsp+48h] [rbp-49h] BYREF
  UNICODE_STRING String1; // [rsp+58h] [rbp-39h] BYREF
  void *v44; // [rsp+68h] [rbp-29h] BYREF
  unsigned __int64 v45; // [rsp+70h] [rbp-21h]
  int v46; // [rsp+78h] [rbp-19h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+80h] [rbp-11h] BYREF
  __int64 v48; // [rsp+98h] [rbp+7h]
  int v49; // [rsp+A0h] [rbp+Fh]
  unsigned int *v50; // [rsp+A8h] [rbp+17h]

  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D4A0;
  v46 = 0;
  Frame.Previous = 0;
  v50 = (unsigned int *)&v46;
  Frame.Flags = 1;
  v48 = 544438355;
  v49 = 409;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  v44 = 0;
  v45 = 0;
  if ( (a1 & 0xFFFFFFFE) != 0 )
  {
    v49 = 420;
    goto LABEL_38;
  }
  if ( !a2 )
  {
    v49 = 421;
    goto LABEL_38;
  }
  if ( !a3 )
  {
    v49 = 422;
LABEL_38:
    FusionpTraceParameterCheck(v6);
    SetLastError(0x57u);
    *v50 = 0;
    v30 = *v50;
    goto LABEL_28;
  }
  v7 = *((_QWORD *)a2 + 5);
  v8 = *((unsigned int *)a2 + 4);
  v9 = 0;
  v37 = v7;
  if ( !(_DWORD)v8 )
    goto LABEL_35;
  Elements = (void *)Windows::VectorTraits<Windows::Identity::Rtl::_ATTRIBUTE const>::AllocateElements((unsigned int)v8);
  if ( !Elements )
  {
    FusionpTraceAllocFailure(v11);
    SetLastError(0xEu);
    *v50 = 0;
    v30 = *v50;
    goto LABEL_28;
  }
  v44 = Elements;
  v45 = v8;
  if ( !(3 * (_DWORD)v8) )
  {
LABEL_35:
    v12 = 0;
    goto LABEL_11;
  }
  v12 = Windows::VectorTraits<Windows::Identity::Rtl::_ATTRIBUTE const>::AllocateElements((unsigned int)(3 * v8));
  if ( v12 )
  {
    v9 = (char *)v12;
LABEL_11:
    v14 = a1 & 1;
    v39 = v14;
    v15 = 0;
    if ( v8 )
    {
      v16 = v37;
      v17 = v12 + 48;
      v40 = v12 + 48;
      v18 = v12 + 24;
      while ( 1 )
      {
        v19 = *(_QWORD **)(v16 + 8 * v15);
        v20 = (char **)((char *)v44 + 24 * v15);
        v21 = (char *)(v18 + 72 * v15);
        v22 = &v9[72 * v15];
        v20[1] = v21;
        v23 = (char *)(v17 + 72 * v15);
        *v20 = v22;
        v20[2] = v23;
        v38 = v21;
        if ( v19[4] && (v34 = v19[1]) != 0 )
        {
          *(_QWORD *)v22 = 2 * v34;
          *((_QWORD *)v22 + 1) = 2LL * v19[1];
          v24 = v19[4];
        }
        else
        {
          *(_QWORD *)v22 = 0;
          v24 = 0;
          *((_QWORD *)v22 + 1) = 0;
        }
        *((_QWORD *)v22 + 2) = v24;
        v25 = (WCHAR *)v19[5];
        if ( v25 && (v26 = v19[2]) != 0 )
        {
          *(_QWORD *)&String2.Length = 1048592;
          *(&String1.MaximumLength + 2) = 0;
          String1.Length = 2 * v26;
          *(_DWORD *)&String1.MaximumLength = (unsigned __int16)(2 * v26);
          String1.Buffer = v25;
          String2.Buffer = aLanguage_0;
          if ( RtlCompareUnicodeString(&String1, &String2, 1u) )
          {
            *(_QWORD *)v38 = 2LL * v19[2];
            *((_QWORD *)v38 + 1) = 2LL * v19[2];
            v27 = (wchar_t *)v19[5];
          }
          else
          {
            *(_QWORD *)v38 = 14;
            v27 = aCulture;
            *((_QWORD *)v38 + 1) = 14;
          }
          *((_QWORD *)v38 + 2) = v27;
          if ( v19[6] )
          {
            v33 = v19[3];
            if ( v33 )
            {
              v17 = v40;
              *(_QWORD *)v23 = 2 * v33;
              *((_QWORD *)v23 + 1) = 2LL * v19[3];
              v28 = v19[6];
              goto LABEL_22;
            }
          }
          v17 = v40;
        }
        else
        {
          *(_QWORD *)v22 = 0;
          *((_QWORD *)v22 + 1) = 0;
          *((_QWORD *)v22 + 2) = 0;
          *(_QWORD *)v21 = 0;
          *((_QWORD *)v21 + 1) = 0;
          *((_QWORD *)v21 + 2) = 0;
        }
        v28 = 0;
        *((_QWORD *)v23 + 1) = 0;
        *(_QWORD *)v23 = 0;
LABEL_22:
        ++v15;
        *((_QWORD *)v23 + 2) = v28;
        if ( v15 >= v8 )
        {
          v14 = v39;
          break;
        }
      }
    }
    v29 = Windows::Identity::Rtl::CreateKeyformFromAttributesIntoBuffer(v14, &v44, 0, a3);
    if ( v29 < 0 )
    {
      v35 = RtlNtStatusToDosErrorNoTeb(v29);
      SetLastError(v35);
      *v50 = 0;
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180076190);
    }
    else
    {
      SetLastError(0);
      *v50 = 1;
    }
    goto LABEL_26;
  }
  FusionpTraceAllocFailure(v13);
  SetLastError(0xEu);
  *v50 = 0;
LABEL_26:
  v30 = *v50;
  if ( v9 )
    operator delete(v9);
LABEL_28:
  v31 = v44;
  if ( v44 )
  {
    v44 = 0;
    v45 = 0;
    operator delete(v31);
  }
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v50 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v30;
}

```

## disassembly

```asm
0x1800265b0  mov     r11, rsp
0x1800265b3  push    rbp
0x1800265b4  push    rbx
0x1800265b5  lea     rbp, [r11-5Fh]
0x1800265b9  sub     rsp, 0D8h
0x1800265c0  mov     rax, cs:__security_cookie
0x1800265c7  xor     rax, rsp
0x1800265ca  mov     [rbp+57h+var_38], rax
0x1800265ce  mov     [r11-20h], r12
0x1800265d2  lea     rax, qword_18006D4A0
0x1800265d9  mov     [r11-30h], r14
0x1800265dd  mov     r12, r8
0x1800265e0  mov     [r11-38h], r15
0x1800265e4  mov     r14d, ecx
0x1800265e7  mov     [rbp+57h+Frame.Context], rax
0x1800265eb  lea     rcx, [rbp+57h+Frame]; Frame
0x1800265ef  xor     r15d, r15d
0x1800265f2  mov     [rbp+57h+var_A8], r8
0x1800265f6  lea     rax, [rbp+57h+var_70]
0x1800265fa  mov     [rbp+57h+var_70], r15d
0x1800265fe  mov     [rbp+57h+Frame.Previous], r15
0x180026602  mov     rbx, rdx
0x180026605  mov     [rbp+57h+var_40], rax
0x180026609  mov     [rbp+57h+Frame.Flags], 1
0x180026610  mov     [rbp+57h+var_50], 20737853h
0x180026618  mov     [rbp+57h+var_48], 199h
0x18002661f  call    cs:__imp_RtlPushFrame
0x180026626  nop     dword ptr [rax+rax+00h]
0x18002662b  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x180026632  jnz     loc_18002690B
0x180026638  mov     [rbp+57h+var_80], r15
0x18002663c  mov     [rbp+57h+var_78], r15
0x180026640  test    r14d, 0FFFFFFFEh
0x180026647  jnz     loc_18002698C
0x18002664d  test    rbx, rbx
0x180026650  jz      loc_180026995
0x180026656  test    r12, r12
0x180026659  jz      loc_18002693B
0x18002665f  mov     rax, [rbx+28h]
0x180026663  mov     ebx, [rbx+10h]
0x180026666  mov     [rsp+0D0h], rdi
0x18002666e  mov     rdi, r15
0x180026671  mov     [rbp+57h+var_C0], rax
0x180026675  test    ebx, ebx
0x180026677  jz      loc_180026915
0x18002667d  mov     ecx, ebx
0x18002667f  call    ?AllocateElements@?$VectorTraits@$$CBU_ATTRIBUTE@Rtl@Identity@Windows@@@Windows@@SAPEBU_ATTRIBUTE@Rtl@Identity@2@_K@Z; Windows::VectorTraits<Windows::Identity::Rtl::_ATTRIBUTE const>::AllocateElements(unsigned __int64)
0x180026684  test    rax, rax
0x180026687  jz      loc_18002699E
0x18002668d  mov     [rbp+57h+var_80], rax
0x180026691  lea     eax, [rbx+rbx*2]
0x180026694  mov     [rbp+57h+var_78], rbx
0x180026698  test    eax, eax
0x18002669a  jz      loc_180026915
0x1800266a0  mov     ecx, eax
0x1800266a2  call    ?AllocateElements@?$VectorTraits@$$CBU_ATTRIBUTE@Rtl@Identity@Windows@@@Windows@@SAPEBU_ATTRIBUTE@Rtl@Identity@2@_K@Z; Windows::VectorTraits<Windows::Identity::Rtl::_ATTRIBUTE const>::AllocateElements(unsigned __int64)
0x1800266a7  test    rax, rax
0x1800266aa  jz      loc_18002696A
0x1800266b0  mov     rdi, rax
0x1800266b3  and     r14d, 1
0x1800266b7  mov     [rsp+0E0h+arg_0], rsi
0x1800266bf  mov     [rbp+57h+var_B8], r14d
0x1800266c3  mov     rsi, r15
0x1800266c6  test    rbx, rbx
0x1800266c9  jz      loc_1800267F7
0x1800266cf  mov     r12, [rbp+57h+var_C0]
0x1800266d3  lea     r9, [rax+30h]
0x1800266d7  mov     [rbp+57h+var_B0], r9
0x1800266db  lea     r14, [rax+18h]
0x1800266df  mov     [rsp+0E0h+var_20], r13
0x1800266e7  mov     r11d, 10h
0x1800266ed  mov     rax, [rbp+57h+var_80]
0x1800266f1  lea     rcx, [rsi+rsi*2]
0x1800266f5  mov     r15, [r12+rsi*8]
0x1800266f9  lea     rdx, [rax+rcx*8]
0x1800266fd  lea     rax, [rsi+rsi*8]
0x180026701  lea     r8, [r14+rax*8]
0x180026705  lea     rcx, [rdi+rax*8]
0x180026709  mov     [rdx+8], r8
0x18002670d  lea     r13, [r9+rax*8]
0x180026711  mov     [rdx], rcx
0x180026714  mov     [rdx+10h], r13
0x180026718  cmp     qword ptr [r15+20h], 0
0x18002671d  mov     [rbp+57h+var_C0], r8
0x180026721  jnz     loc_1800269C6
0x180026727  xor     r10d, r10d
0x18002672a  mov     [rcx], r10
0x18002672d  mov     eax, r10d
0x180026730  mov     [rcx+8], r10
0x180026734  mov     [rcx+10h], rax
0x180026738  mov     rdx, [r15+28h]
0x18002673c  test    rdx, rdx
0x18002673f  jz      loc_18002691D
0x180026745  mov     rax, [r15+10h]
0x180026749  test    rax, rax
0x18002674c  jz      loc_18002691D
0x180026752  add     ax, ax
0x180026755  mov     qword ptr [rbp+57h+String2.Length], 100010h
0x18002675d  xorps   xmm0, xmm0
0x180026760  lea     rcx, [rbp+57h+String1]; String1
0x180026764  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x180026768  mov     [rbp+57h+String1.Length], ax
0x18002676c  mov     r8b, 1; CaseInsensitive
0x18002676f  mov     [rbp+57h+String1.MaximumLength], ax
0x180026773  lea     rax, aLanguage_0; "language"
0x18002677a  mov     [rbp+57h+String1.Buffer], rdx
0x18002677e  lea     rdx, [rbp+57h+String2]; String2
0x180026782  mov     [rbp+57h+String2.Buffer], rax
0x180026786  call    cs:__imp_RtlCompareUnicodeString
0x18002678d  nop     dword ptr [rax+rax+00h]
0x180026792  mov     rcx, [rbp+57h+var_C0]
0x180026796  test    eax, eax
0x180026798  jnz     loc_1800268B8
0x18002679e  mov     qword ptr [rcx], 0Eh
0x1800267a5  lea     rax, aCulture; "culture"
0x1800267ac  mov     qword ptr [rcx+8], 0Eh
0x1800267b4  mov     [rcx+10h], rax
0x1800267b8  cmp     qword ptr [r15+30h], 0
0x1800267bd  jnz     loc_1800268D6
0x1800267c3  mov     r9, [rbp+57h+var_B0]
0x1800267c7  xor     r15d, r15d
0x1800267ca  mov     r11d, 10h
0x1800267d0  mov     rax, r15
0x1800267d3  mov     [r13+8], r15
0x1800267d7  mov     [r13+0], r15
0x1800267db  inc     rsi
0x1800267de  mov     [r13+10h], rax
0x1800267e2  cmp     rsi, rbx
0x1800267e5  jb      loc_1800266ED
0x1800267eb  mov     r13, [rsp+0E0h+var_20]
0x1800267f3  mov     r14d, [rbp+57h+var_B8]
0x1800267f7  mov     r9, [rbp+57h+var_A8]
0x1800267fb  lea     rdx, [rbp+57h+var_80]
0x1800267ff  xor     r8d, r8d
0x180026802  mov     ecx, r14d
0x180026805  call    cs:__imp_?CreateKeyformFromAttributesIntoBuffer@Rtl@Identity@Windows@@YAJKAEBU?$Vector@$$CBU_ATTRIBUTE@Rtl@Identity@Windows@@@3@_KPEAU_LUNICODE_STRING@@@Z; Windows::Identity::Rtl::CreateKeyformFromAttributesIntoBuffer(ulong,Windows::Vector<Windows::Identity::Rtl::_ATTRIBUTE const> const &,unsigned __int64,_LUNICODE_STRING *)
0x18002680c  nop     dword ptr [rax+rax+00h]
0x180026811  mov     rsi, [rsp+0E0h+arg_0]
0x180026819  test    eax, eax
0x18002681b  js      loc_1800269ED
0x180026821  xor     ecx, ecx; dwErrCode
0x180026823  call    cs:__imp_SetLastError
0x18002682a  nop     dword ptr [rax+rax+00h]
0x18002682f  mov     rax, [rbp+57h+var_40]
0x180026833  mov     dword ptr [rax], 1
0x180026839  mov     rax, [rbp+57h+var_40]
0x18002683d  mov     ebx, [rax]
0x18002683f  test    rdi, rdi
0x180026842  jz      short loc_18002684C
0x180026844  mov     rcx, rdi; void *
0x180026847  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002684c  mov     rdi, [rsp+0D0h]
0x180026854  mov     rcx, [rbp+57h+var_80]; void *
0x180026858  mov     r14, [rsp+0E0h+var_28]
0x180026860  mov     r12, [rsp+0E0h+var_18]
0x180026868  test    rcx, rcx
0x18002686b  jz      short loc_18002687A
0x18002686d  mov     [rbp+57h+var_80], r15
0x180026871  mov     [rbp+57h+var_78], r15
0x180026875  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002687a  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180026881  mov     r15, [rsp+0E0h+var_30]
0x180026889  jnz     loc_180026A21
0x18002688f  lea     rcx, [rbp+57h+Frame]; Frame
0x180026893  call    cs:__imp_RtlPopFrame
0x18002689a  nop     dword ptr [rax+rax+00h]
0x18002689f  mov     eax, ebx
0x1800268a1  mov     rcx, [rbp+57h+var_38]
0x1800268a5  xor     rcx, rsp; StackCookie
0x1800268a8  call    __security_check_cookie
0x1800268ad  add     rsp, 0D8h
0x1800268b4  pop     rbx
0x1800268b5  pop     rbp
0x1800268b6  retn
0x1800268b8  mov     rax, [r15+10h]
0x1800268bc  add     rax, rax
0x1800268bf  mov     [rcx], rax
0x1800268c2  mov     rax, [r15+10h]
0x1800268c6  add     rax, rax
0x1800268c9  mov     [rcx+8], rax
0x1800268cd  mov     rax, [r15+28h]
0x1800268d1  jmp     loc_1800267B4
0x1800268d6  mov     rax, [r15+18h]
0x1800268da  test    rax, rax
0x1800268dd  jz      loc_1800267C3
0x1800268e3  mov     r9, [rbp+57h+var_B0]
0x1800268e7  add     rax, rax
0x1800268ea  mov     [r13+0], rax
0x1800268ee  mov     r11d, 10h
0x1800268f4  mov     rax, [r15+18h]
0x1800268f8  add     rax, rax
0x1800268fb  mov     [r13+8], rax
0x1800268ff  mov     rax, [r15+30h]
0x180026903  xor     r15d, r15d
0x180026906  jmp     loc_1800267DB
0x18002690b  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180026910  jmp     loc_180026638
0x180026915  mov     rax, r15
0x180026918  jmp     loc_1800266B3
0x18002691d  xor     r15d, r15d
0x180026920  mov     [rcx], r15
0x180026923  mov     [rcx+8], r15
0x180026927  mov     [rcx+10h], r15
0x18002692b  mov     [r8], r15
0x18002692e  mov     [r8+8], r15
0x180026932  mov     [r8+10h], r15
0x180026936  jmp     loc_1800267D0
0x18002693b  mov     [rbp+57h+var_48], 1A6h
0x180026942  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180026947  mov     ecx, 57h ; 'W'; dwErrCode
0x18002694c  call    cs:__imp_SetLastError
0x180026953  nop     dword ptr [rax+rax+00h]
0x180026958  mov     rax, [rbp+57h+var_40]
0x18002695c  mov     [rax], r15d
0x18002695f  mov     rax, [rbp+57h+var_40]
0x180026963  mov     ebx, [rax]
0x180026965  jmp     loc_180026854
0x18002696a  call    ?FusionpTraceAllocFailure@@YAXPEBD@Z; FusionpTraceAllocFailure(char const *)
0x18002696f  mov     ecx, 0Eh; dwErrCode
0x180026974  call    cs:__imp_SetLastError
0x18002697b  nop     dword ptr [rax+rax+00h]
0x180026980  mov     rax, [rbp+57h+var_40]
0x180026984  mov     [rax], r15d
0x180026987  jmp     loc_180026839
0x18002698c  mov     [rbp+57h+var_48], 1A4h
0x180026993  jmp     short loc_180026942
0x180026995  mov     [rbp+57h+var_48], 1A5h
0x18002699c  jmp     short loc_180026942
0x18002699e  call    ?FusionpTraceAllocFailure@@YAXPEBD@Z; FusionpTraceAllocFailure(char const *)
0x1800269a3  mov     ecx, 0Eh; dwErrCode
0x1800269a8  call    cs:__imp_SetLastError
0x1800269af  nop     dword ptr [rax+rax+00h]
0x1800269b4  mov     rax, [rbp+57h+var_40]
0x1800269b8  mov     [rax], r15d
0x1800269bb  mov     rax, [rbp+57h+var_40]
0x1800269bf  mov     ebx, [rax]
0x1800269c1  jmp     loc_18002684C
0x1800269c6  mov     rax, [r15+8]
0x1800269ca  test    rax, rax
0x1800269cd  jz      loc_180026727
0x1800269d3  add     rax, rax
0x1800269d6  mov     [rcx], rax
0x1800269d9  mov     rax, [r15+8]
0x1800269dd  add     rax, rax
0x1800269e0  mov     [rcx+8], rax
0x1800269e4  mov     rax, [r15+20h]
0x1800269e8  jmp     loc_180026734
0x1800269ed  mov     ecx, eax; Status
0x1800269ef  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800269f6  nop     dword ptr [rax+rax+00h]
0x1800269fb  mov     ecx, eax; dwErrCode
0x1800269fd  call    cs:__imp_SetLastError
0x180026a04  nop     dword ptr [rax+rax+00h]
0x180026a09  mov     rax, [rbp+57h+var_40]
0x180026a0d  lea     rcx, off_180076190; struct _CALL_SITE_INFO *
0x180026a14  mov     [rax], r15d
0x180026a17  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x180026a1c  jmp     loc_180026839
0x180026a21  mov     rax, [rbp+57h+var_40]
0x180026a25  cmp     dword ptr [rax], 0
0x180026a28  jz      short loc_180026A36
0x180026a2a  xor     ecx, ecx; char *
0x180026a2c  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180026a31  jmp     loc_18002688F
0x180026a36  call    cs:__imp_GetLastError
0x180026a3d  nop     dword ptr [rax+rax+00h]
0x180026a42  mov     ecx, eax; unsigned int
0x180026a44  xor     edx, edx; Format
0x180026a46  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180026a4b  jmp     loc_18002688F
```
