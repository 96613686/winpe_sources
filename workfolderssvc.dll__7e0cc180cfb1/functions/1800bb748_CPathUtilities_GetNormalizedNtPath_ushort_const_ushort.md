# CPathUtilities::GetNormalizedNtPath(ushort const *,ushort * *)

- ea: `0x1800bb748`
- end: `0x1800bb940`
- name: `?GetNormalizedNtPath@CPathUtilities@@SAJPEBGPEAPEAG@Z`
- size: `504`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `31`
- callee_count: `8`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800593c8`
- `0x18008cad0`
- `0x18008d1c0`
- `0x18008e660`
- `0x18008f34c`
- `0x18008faa4`
- `0x180090710`
- `0x180090ac0`
- `0x180090c88`
- `0x180091408`
- `0x180091acc`
- `0x180091fc0`
- `0x180092400`
- `0x180092750`
- `0x180092d2c`
- `0x180093f50`
- `0x1800942b0`
- `0x1800946c0`
- `0x1800950b4`
- `0x180095750`
- `0x180096930`
- `0x18009859c`
- `0x18010beb4`
- `0x18010d440`
- `0x18010e248`
- `0x18010eae8`
- `0x18010fd2c`
- `0x18011038c`
- `0x180110c70`
- `0x1801153ec`
- `0x1801163e0`

## callees

- `0x180007e10`
- `0x180008080`
- `0x180011314`
- `0x180058d88`
- `0x18008b634`
- `0x1800bb748`
- `0x1800bbd94`
- `0x1800bbe18`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800bb822`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800bb840`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800bb822`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800bb840`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800bb857`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800bb857`
- `ntdll!RtlFreeUnicodeString` at `0x1800bb90e`
- `ntdll!RtlFreeUnicodeString` at `0x1800bb90e`

## string_xrefs

- `0x1800bb7c0`: `CPathUtilities::GetNormalizedNtPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPathUtilities::GetNormalizedNtPath(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  _BYTE *v4; // rax
  char v5; // cl
  __int16 v6; // ax
  unsigned int v7; // eax
  unsigned __int64 v8; // rbx
  bool v9; // sf
  unsigned __int16 *v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // ebx
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-30h] BYREF
  int v15; // [rsp+30h] [rbp-20h] BYREF
  int v16; // [rsp+34h] [rbp-1Ch]
  char v17; // [rsp+38h] [rbp-18h]
  const char *v18; // [rsp+40h] [rbp-10h]
  __int64 v19; // [rsp+48h] [rbp-8h]
  unsigned __int16 *v20; // [rsp+70h] [rbp+20h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, WPP_0e035964b16e3dba2f65f7eff446a590_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( (v4[68] & 0x20) == 0 || (v5 = 1, v4[65] < 6u) )
    v5 = 0;
  v15 = 0;
  v16 = 439;
  v17 = v5;
  v18 = "CPathUtilities::GetNormalizedNtPath";
  v19 = 0;
  v20 = 0;
  UnicodeString = 0;
  if ( a2 )
    *a2 = 0;
  v6 = 450;
  if ( !a1 || (LOWORD(v16) = 450, v6 = 451, !a2) )
  {
    v15 = -2147024809;
    goto LABEL_12;
  }
  v15 = 0;
  LOWORD(v16) = 451;
  if ( (unsigned int)_o__wcsnicmp(a1, L"\\??\\", 4) && (unsigned int)_o__wcsnicmp(a1, L"\\device\\", 8) )
  {
    v7 = RtlDosPathNameToNtPathName_U_WithStatus(a1, &UnicodeString, 0, 0);
    v15 = HRESULTFromNTSTATUS(v7);
    v6 = 468;
    if ( v15 < 0 )
      goto LABEL_12;
    LOWORD(v16) = 468;
    v8 = (unsigned __int64)UnicodeString.Length >> 1;
    v15 = CEcsMemPtr<unsigned short,0>::AllocBytes((void **)&v20, 2 * (v8 + 1));
    v6 = 471;
    if ( v15 < 0 )
      goto LABEL_12;
    LOWORD(v16) = 471;
    v15 = StringCchCopyNW(v20, v8 + 1, UnicodeString.Buffer, v8);
    v9 = v15 < 0;
    v6 = 476;
  }
  else
  {
    v15 = CSyncCoreStringUtils::StringCopyAlloc(a1, &v20);
    v9 = v15 < 0;
    v6 = 459;
  }
  if ( v9 )
  {
LABEL_12:
    HIWORD(v16) = v6;
    goto LABEL_26;
  }
  LOWORD(v16) = v6;
  v10 = v20;
  v11 = -1;
  do
    ++v11;
  while ( v20[v11] );
  if ( v20[v11 - 1] == 92 )
  {
    v20[v11 - 1] = 0;
    v10 = v20;
  }
  v20 = 0;
  *a2 = v10;
LABEL_26:
  RtlFreeUnicodeString(&UnicodeString);
  v12 = v15;
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&v20);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v15);
  return v12;
}

```

## disassembly

```asm
0x1800bb748  mov     [rsp-18h+arg_8], rbx
0x1800bb74d  mov     [rsp-18h+arg_10], rsi
0x1800bb752  push    rbp
0x1800bb753  push    rdi
0x1800bb754  push    r14
0x1800bb756  mov     rbp, rsp
0x1800bb759  sub     rsp, 50h
0x1800bb75d  mov     rdi, rdx
0x1800bb760  mov     rbx, rcx
0x1800bb763  lea     rcx, WPP_GLOBAL_Control
0x1800bb76a  mov     rax, cs:WPP_GLOBAL_Control
0x1800bb771  cmp     rax, rcx
0x1800bb774  jz      short loc_1800BB79E
0x1800bb776  test    byte ptr [rax+44h], 20h
0x1800bb77a  jz      short loc_1800BB79E
0x1800bb77c  cmp     byte ptr [rax+41h], 6
0x1800bb780  jb      short loc_1800BB79E
0x1800bb782  mov     edx, 0Fh
0x1800bb787  lea     r8, WPP_0e035964b16e3dba2f65f7eff446a590_Traceguids
0x1800bb78e  mov     rcx, [rax+38h]
0x1800bb792  call    WPP_SF_
0x1800bb797  mov     rax, cs:WPP_GLOBAL_Control
0x1800bb79e  xor     r14d, r14d
0x1800bb7a1  test    byte ptr [rax+44h], 20h
0x1800bb7a5  jz      short loc_1800BB7AF
0x1800bb7a7  cmp     byte ptr [rax+41h], 6
0x1800bb7ab  mov     cl, 1
0x1800bb7ad  jnb     short loc_1800BB7B2
0x1800bb7af  mov     cl, r14b
0x1800bb7b2  mov     [rbp+var_20], r14d
0x1800bb7b6  mov     [rbp+var_1C], 1B7h
0x1800bb7bd  mov     [rbp+var_18], cl
0x1800bb7c0  lea     rax, aCpathutilities_1; "CPathUtilities::GetNormalizedNtPath"
0x1800bb7c7  mov     [rbp+var_10], rax
0x1800bb7cb  mov     [rbp+var_8], r14
0x1800bb7cf  mov     [rbp+arg_0], r14
0x1800bb7d3  xorps   xmm0, xmm0
0x1800bb7d6  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x1800bb7da  test    rdi, rdi
0x1800bb7dd  jz      short loc_1800BB7E2
0x1800bb7df  mov     [rdi], r14
0x1800bb7e2  mov     eax, 1C2h
0x1800bb7e7  test    rbx, rbx
0x1800bb7ea  jnz     short loc_1800BB7FC
0x1800bb7ec  mov     [rbp+var_20], 80070057h
0x1800bb7f3  mov     word ptr [rbp+var_1C+2], ax
0x1800bb7f7  jmp     loc_1800BB90A
0x1800bb7fc  mov     word ptr [rbp+var_1C], ax
0x1800bb800  mov     eax, 1C3h
0x1800bb805  test    rdi, rdi
0x1800bb808  jz      short loc_1800BB7EC
0x1800bb80a  mov     [rbp+var_20], r14d
0x1800bb80e  mov     word ptr [rbp+var_1C], ax
0x1800bb812  mov     r8d, 4
0x1800bb818  lea     rdx, asc_18015D9C0; "\\??\\"
0x1800bb81f  mov     rcx, rbx
0x1800bb822  call    cs:__imp__o__wcsnicmp
0x1800bb828  test    eax, eax
0x1800bb82a  jz      loc_1800BB8BF
0x1800bb830  mov     r8d, 8
0x1800bb836  lea     rdx, aDevice; "\\device\\"
0x1800bb83d  mov     rcx, rbx
0x1800bb840  call    cs:__imp__o__wcsnicmp
0x1800bb846  test    eax, eax
0x1800bb848  jz      short loc_1800BB8BF
0x1800bb84a  xor     r9d, r9d
0x1800bb84d  xor     r8d, r8d
0x1800bb850  lea     rdx, [rbp+UnicodeString]
0x1800bb854  mov     rcx, rbx
0x1800bb857  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800bb85d  mov     ecx, eax
0x1800bb85f  call    HRESULTFromNTSTATUS
0x1800bb864  mov     [rbp+var_20], eax
0x1800bb867  test    eax, eax
0x1800bb869  mov     eax, 1D4h
0x1800bb86e  js      short loc_1800BB7F3
0x1800bb870  mov     word ptr [rbp+var_1C], ax
0x1800bb874  movzx   ebx, [rbp+UnicodeString.Length]
0x1800bb878  shr     rbx, 1
0x1800bb87b  lea     rsi, [rbx+1]
0x1800bb87f  lea     rdx, [rsi+rsi]; unsigned __int64
0x1800bb883  lea     rcx, [rbp+arg_0]; void **
0x1800bb887  call    ?AllocBytes@?$CEcsMemPtr@G$0A@@@QEAAJ_K@Z; CEcsMemPtr<ushort,0>::AllocBytes(unsigned __int64)
0x1800bb88c  mov     [rbp+var_20], eax
0x1800bb88f  test    eax, eax
0x1800bb891  mov     eax, 1D7h
0x1800bb896  js      loc_1800BB7F3
0x1800bb89c  mov     word ptr [rbp+var_1C], ax
0x1800bb8a0  mov     r9, rbx; unsigned __int64
0x1800bb8a3  mov     r8, [rbp+UnicodeString.Buffer]; unsigned __int16 *
0x1800bb8a7  mov     rdx, rsi; unsigned __int64
0x1800bb8aa  mov     rcx, [rbp+arg_0]; unsigned __int16 *
0x1800bb8ae  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800bb8b3  mov     [rbp+var_20], eax
0x1800bb8b6  test    eax, eax
0x1800bb8b8  mov     eax, 1DCh
0x1800bb8bd  jmp     short loc_1800BB8D5
0x1800bb8bf  lea     rdx, [rbp+arg_0]; unsigned __int16 **
0x1800bb8c3  mov     rcx, rbx; unsigned __int16 *
0x1800bb8c6  call    ?StringCopyAlloc@CSyncCoreStringUtils@@SAJPEBGPEAPEAG@Z; CSyncCoreStringUtils::StringCopyAlloc(ushort const *,ushort * *)
0x1800bb8cb  mov     [rbp+var_20], eax
0x1800bb8ce  test    eax, eax
0x1800bb8d0  mov     eax, 1CBh
0x1800bb8d5  js      loc_1800BB7F3
0x1800bb8db  mov     word ptr [rbp+var_1C], ax
0x1800bb8df  mov     rcx, [rbp+arg_0]
0x1800bb8e3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800bb8e7  inc     rdx
0x1800bb8ea  cmp     [rcx+rdx*2], r14w
0x1800bb8ef  jnz     short loc_1800BB8E7
0x1800bb8f1  cmp     word ptr [rcx+rdx*2-2], 5Ch ; '\'
0x1800bb8f7  jnz     short loc_1800BB903
0x1800bb8f9  mov     [rcx+rdx*2-2], r14w
0x1800bb8ff  mov     rcx, [rbp+arg_0]
0x1800bb903  mov     [rbp+arg_0], r14
0x1800bb907  mov     [rdi], rcx
0x1800bb90a  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x1800bb90e  call    cs:__imp_RtlFreeUnicodeString
0x1800bb914  mov     ebx, [rbp+var_20]
0x1800bb917  lea     rcx, [rbp+arg_0]
0x1800bb91b  call    ??1?$CEcsMemPtr@G$0A@@@QEAA@XZ; CEcsMemPtr<ushort,0>::~CEcsMemPtr<ushort,0>(void)
0x1800bb920  lea     rcx, [rbp+var_20]; this
0x1800bb924  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800bb929  mov     eax, ebx
0x1800bb92b  lea     r11, [rsp+50h+var_s0]
0x1800bb930  mov     rbx, [r11+28h]
0x1800bb934  mov     rsi, [r11+30h]
0x1800bb938  mov     rsp, r11
0x1800bb93b  pop     r14
0x1800bb93d  pop     rdi
0x1800bb93e  pop     rbp
0x1800bb93f  retn
```
