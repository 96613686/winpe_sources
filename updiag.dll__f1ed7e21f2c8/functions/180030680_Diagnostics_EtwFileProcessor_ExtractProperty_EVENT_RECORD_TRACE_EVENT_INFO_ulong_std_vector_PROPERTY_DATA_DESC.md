# Diagnostics::EtwFileProcessor::ExtractProperty(_EVENT_RECORD *,_TRACE_EVENT_INFO *,ulong,std::vector<_PROPERTY_DATA_DESCRIPTOR,std::allocator<_PROPERTY_DATA_DESCRIPTOR>> &,Diagnostics::OTelLogRecord &,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180030680`
- end: `0x180030c13`
- name: `?ExtractProperty@EtwFileProcessor@Diagnostics@@CAJPEAU_EVENT_RECORD@@PEAU_TRACE_EVENT_INFO@@KAEAV?$vector@U_PROPERTY_DATA_DESCRIPTOR@@V?$allocator@U_PROPERTY_DATA_DESCRIPTOR@@@std@@@std@@AEAVOTelLogRecord@2@KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@6@@Z`
- size: `1427`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: ``

## callers

- `0x180030680`
- `0x180031154`

## callees

- `0x180018eec`
- `0x180018f68`
- `0x180019080`
- `0x18001adcc`
- `0x180020dc8`
- `0x18002a204`
- `0x18003039c`
- `0x180030680`
- `0x180030c1c`
- `0x18003b934`
- `0x180046e60`
- `0x180046edc`
- `0x180054360`
- `0x18006664c`
- `0x180066764`
- `0x18008fe00`

## import_xrefs

- `tdh!TdhGetProperty` at `0x1800309d4`
- `tdh!TdhGetProperty` at `0x1800309d4`
- `tdh!TdhGetPropertySize` at `0x180030943`
- `tdh!TdhGetPropertySize` at `0x180030943`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Diagnostics::EtwFileProcessor::ExtractProperty(
        struct _EVENT_RECORD *a1,
        __int64 a2,
        unsigned int a3,
        PROPERTY_DATA_DESCRIPTOR **a4,
        Diagnostics::OTelLogRecord *a5,
        int a6,
        __int64 a7)
{
  unsigned int v8; // ebx
  __int64 v9; // r13
  ULONGLONG v11; // r12
  unsigned __int64 v12; // r8
  ULONG v13; // edi
  const void *v14; // rdx
  PROPERTY_DATA_DESCRIPTOR *v15; // rax
  char v16; // si
  __int64 v17; // rcx
  PROPERTY_DATA_DESCRIPTOR *v18; // rdx
  const char *v19; // rax
  unsigned int v20; // esi
  unsigned int v21; // edi
  int v22; // ebx
  int v23; // r13d
  PROPERTY_DATA_DESCRIPTOR *pPropertyData; // rax
  __int64 v25; // rsi
  struct _EVENT_RECORD *v26; // r12
  TDHSTATUS PropertySize; // eax
  const char *v28; // r9
  const char *v29; // rax
  TDHSTATUS Property; // eax
  const char *v31; // rdx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  ULONG v41; // r12d
  ULONG i; // esi
  __int64 v43; // rdi
  __int128 *p_Src; // rax
  char **v45; // rdx
  PROPERTY_DATA_DESCRIPTOR v46; // [rsp+50h] [rbp-B0h] BYREF
  PEVENT_RECORD pEvent; // [rsp+70h] [rbp-90h]
  Diagnostics::OTelLogRecord *v48; // [rsp+78h] [rbp-88h]
  _QWORD v49[2]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v50[2]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v51[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v52[32]; // [rsp+D0h] [rbp-30h] BYREF
  ULONG BufferSize; // [rsp+F0h] [rbp-10h] BYREF
  char *v54[2]; // [rsp+F8h] [rbp-8h] BYREF
  PROPERTY_DATA_DESCRIPTOR v55; // [rsp+108h] [rbp+8h]
  __int128 Src; // [rsp+118h] [rbp+18h] BYREF
  __int128 v57; // [rsp+128h] [rbp+28h]
  PBYTE pBuffer[2]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v59; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v49[0] = a2;
  pEvent = a1;
  v48 = a5;
  v8 = 0;
  v9 = a2 + 24LL * a3;
  if ( !*(_DWORD *)(v9 + 116) )
    return 1;
  v11 = a2 + *(unsigned int *)(v9 + 116);
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)(v11 + 2 * v12) );
  v13 = 2;
  v14 = (const void *)(a2 + *(unsigned int *)(v9 + 116));
  if ( *(_QWORD *)(a7 + 16) )
  {
    memset(v50, 0, sizeof(v50));
    std::wstring::_Construct<1,wchar_t const *>(v50, v14, v12);
    v17 = *(_QWORD *)(a7 + 16);
    if ( v17 == 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    std::wstring::wstring(v52, v17, L".", 1);
    v15 = (PROPERTY_DATA_DESCRIPTOR *)std::operator+<wchar_t>(v51, v52, v50);
    v16 = 30;
  }
  else
  {
    memset(&v46, 0, 32);
    std::wstring::_Construct<1,wchar_t const *>(&v46, v14, v12);
    v15 = &v46;
    v16 = 1;
  }
  *(_OWORD *)v54 = 0;
  v55 = (PROPERTY_DATA_DESCRIPTOR)0LL;
  *(PROPERTY_DATA_DESCRIPTOR *)v54 = *v15;
  v55 = v15[1];
  LOWORD(v15->PropertyName) = 0;
  v15[1].PropertyName = 0;
  *(_QWORD *)&v15[1].ArrayIndex = 7;
  if ( (v16 & 8) != 0 )
  {
    v16 &= ~8u;
    std::wstring::~wstring((__int64)v51);
  }
  if ( (v16 & 4) != 0 )
  {
    v16 &= ~4u;
    std::wstring::~wstring((__int64)v52);
  }
  if ( (v16 & 2) != 0 )
  {
    v16 &= ~2u;
    std::wstring::~wstring((__int64)v50);
  }
  if ( (v16 & 1) != 0 )
    std::wstring::~wstring((__int64)&v46);
  v46.PropertyName = v11;
  *(_QWORD *)&v46.ArrayIndex = 0xFFFFFFFFLL;
  v18 = a4[1];
  if ( v18 == a4[2] )
  {
    std::vector<_PROPERTY_DATA_DESCRIPTOR>::_Emplace_reallocate<_PROPERTY_DATA_DESCRIPTOR const &>(a4, v18, &v46);
  }
  else
  {
    *v18 = v46;
    ++a4[1];
  }
  *(_QWORD *)&v50[0] = a4;
  BYTE8(v50[0]) = 1;
  if ( (*(_BYTE *)(v9 + 112) & 1) != 0 )
  {
    if ( a6 )
    {
      v20 = *(unsigned __int16 *)(v9 + 122);
      v21 = 0;
      if ( *(_WORD *)(v9 + 122) )
      {
        v22 = *(unsigned __int16 *)(v9 + 120);
        v23 = v49[0];
        do
        {
          Diagnostics::EtwFileProcessor::ExtractProperty(
            (_DWORD)pEvent,
            v23,
            v21 + v22,
            (_DWORD)a4,
            (__int64)v48,
            a6 - 1,
            (__int64)v54);
          ++v21;
        }
        while ( v21 < v20 );
        v8 = 0;
      }
    }
    else
    {
      v19 = (const char *)v54;
      if ( *(_QWORD *)&v55.ArrayIndex > 7u )
        v19 = v54[0];
      v8 = -2147483637;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x2DE,
        (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\EtwFileProcessor.hpp",
        (const char *)0x8000000BLL,
        (int)"Max struct depth reached, skipping: %ls",
        v19);
    }
    goto LABEL_72;
  }
  pPropertyData = *a4;
  v25 = a4[1] - *a4;
  BufferSize = 0;
  v26 = pEvent;
  PropertySize = TdhGetPropertySize(pEvent, 0, 0, v25, pPropertyData, &BufferSize);
  v28 = (const char *)PropertySize;
  if ( PropertySize )
  {
    v29 = (const char *)v54;
    if ( *(_QWORD *)&v55.ArrayIndex > 7u )
      v29 = v54[0];
    v8 = wil::details::in1diag3::Return_Win32Msg(
           retaddr,
           (void *)0x2F0,
           (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\EtwFileProcessor.hpp",
           v28,
           (unsigned int)"TdhGetPropertySize failed for: %ls",
           v29);
    goto LABEL_72;
  }
  if ( BufferSize )
  {
    *(_OWORD *)pBuffer = 0;
    v59 = 0;
    std::vector<unsigned char>::vector<unsigned char>(pBuffer, BufferSize);
    Property = TdhGetProperty(v26, 0, 0, v25, *a4, BufferSize, pBuffer[0]);
    if ( Property )
    {
      v31 = (const char *)v54;
      if ( *(_QWORD *)&v55.ArrayIndex > 7u )
        v31 = v54[0];
      v8 = wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             (void *)0x2F9,
             (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\EtwFileProcessor.hpp",
             (const char *)Property,
             (unsigned int)"TdhGetProperty failed for: %ls",
             v31);
LABEL_71:
      std::vector<char>::~vector<char>(pBuffer);
      goto LABEL_72;
    }
    Src = 0;
    *(_QWORD *)&v57 = 0;
    *((_QWORD *)&v57 + 1) = 7;
    LOWORD(Src) = 0;
    v32 = *(unsigned __int16 *)(v9 + 120);
    if ( v32 > 9 )
    {
      v37 = v32 - 10;
      if ( v37 )
      {
        v38 = v37 - 1;
        if ( !v38 )
        {
LABEL_45:
          v13 = 4;
          goto LABEL_55;
        }
        v39 = v38 - 1;
        if ( v39 )
        {
          v40 = v39 - 1;
          if ( !v40 )
          {
LABEL_53:
            v13 = 1;
            goto LABEL_55;
          }
          if ( v40 != 2 )
          {
LABEL_51:
            v13 = 0;
            goto LABEL_55;
          }
          v13 = 16;
LABEL_55:
          if ( (*(_BYTE *)(v9 + 112) & 6) != 0 && v13 && BufferSize > v13 )
          {
            v41 = BufferSize / v13;
            for ( i = 0; i < v41; ++i )
            {
              if ( i )
                std::wstring::append(&Src);
              Diagnostics::EtwFileProcessor::FormatPropertyValue(v51, v9 + 112, &pBuffer[0][i * v13], v13);
              std::wstring::append(&Src);
              std::wstring::~wstring((__int64)v51);
            }
          }
          else
          {
            v43 = Diagnostics::EtwFileProcessor::FormatPropertyValue(v51, v9 + 112, pBuffer[0], BufferSize);
            if ( &Src != (__int128 *)v43 )
            {
              std::wstring::~wstring((__int64)&Src);
              Src = *(_OWORD *)v43;
              v57 = *(_OWORD *)(v43 + 16);
              *(_QWORD *)(v43 + 16) = 0;
              *(_QWORD *)(v43 + 24) = 7;
              *(_WORD *)v43 = 0;
            }
            std::wstring::~wstring((__int64)v51);
          }
          p_Src = &Src;
          if ( *((_QWORD *)&v57 + 1) > 7u )
            p_Src = (__int128 *)Src;
          v45 = v54;
          if ( *(_QWORD *)&v55.ArrayIndex > 7u )
            v45 = (char **)v54[0];
          v46.PropertyName = (ULONGLONG)p_Src;
          *(_QWORD *)&v46.ArrayIndex = v57;
          v49[0] = v45;
          v49[1] = v55.PropertyName;
          Diagnostics::OTelLogRecord::AddAttribute(v48, v49, &v46);
          Diagnostics::EtwFileProcessor::PostProcessAttributes(v48, (wchar_t *)v54, (wchar_t *)&Src);
          std::wstring::~wstring((__int64)&Src);
          goto LABEL_71;
        }
      }
    }
    else if ( v32 != 9 )
    {
      v33 = v32 - 3;
      if ( v33 )
      {
        v34 = v33 - 1;
        if ( v34 )
        {
          v35 = v34 - 1;
          if ( !v35 )
            goto LABEL_55;
          v36 = v35 - 1;
          if ( !v36 )
            goto LABEL_55;
          if ( v36 - 1 <= 1 )
            goto LABEL_45;
          goto LABEL_51;
        }
      }
      goto LABEL_53;
    }
    v13 = 8;
    goto LABEL_55;
  }
LABEL_72:
  --a4[1];
  std::wstring::~wstring((__int64)v54);
  return v8;
}

```

## disassembly

```asm
0x180030680  push    rbp
0x180030682  push    rbx
0x180030683  push    rsi
0x180030684  push    rdi
0x180030685  push    r12
0x180030687  push    r13
0x180030689  push    r15
0x18003068b  lea     rbp, [rsp-60h]
0x180030690  sub     rsp, 160h
0x180030697  mov     rax, cs:__security_cookie
0x18003069e  xor     rax, rsp
0x1800306a1  mov     [rbp+90h+var_40], rax
0x1800306a5  mov     r15, r9
0x1800306a8  mov     [rbp+90h+var_110], rdx
0x1800306ac  mov     [rsp+190h+pEvent], rcx
0x1800306b1  mov     rsi, [rbp+90h+arg_30]
0x1800306b8  mov     rax, [rbp+90h+arg_20]
0x1800306bf  mov     [rsp+190h+var_118], rax
0x1800306c4  xor     ebx, ebx
0x1800306c6  mov     [rsp+190h+var_150], ebx
0x1800306ca  mov     eax, r8d
0x1800306cd  lea     rcx, [rax+rax*2]
0x1800306d1  lea     r13, [rdx+rcx*8]
0x1800306d5  cmp     [r13+74h], ebx
0x1800306d9  jnz     short loc_1800306E3
0x1800306db  lea     eax, [rbx+1]
0x1800306de  jmp     loc_180030BEF
0x1800306e3  mov     r12d, [r13+74h]
0x1800306e7  add     r12, rdx
0x1800306ea  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800306ee  inc     r8
0x1800306f1  cmp     [r12+r8*2], bx
0x1800306f6  jnz     short loc_1800306EE
0x1800306f8  mov     edi, 2
0x1800306fd  xorps   xmm0, xmm0
0x180030700  xorps   xmm1, xmm1
0x180030703  mov     rdx, r12
0x180030706  cmp     [rsi+10h], rbx
0x18003070a  jnz     short loc_18003072E
0x18003070c  movups  xmmword ptr [rsp+190h+var_140.PropertyName], xmm0
0x180030711  movdqu  [rsp+190h+var_130], xmm1
0x180030717  lea     rcx, [rsp+190h+var_140]
0x18003071c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180030721  lea     rax, [rsp+190h+var_140]
0x180030726  lea     esi, [rdi-1]
0x180030729  jmp     loc_1800307AF
0x18003072e  movups  [rbp+90h+var_100], xmm0
0x180030732  movdqu  [rbp+90h+var_F0], xmm1
0x180030737  lea     rcx, [rbp+90h+var_100]
0x18003073b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180030740  nop
0x180030741  mov     [rsp+190h+var_150], edi
0x180030745  mov     rcx, [rsi+10h]
0x180030749  mov     rax, 7FFFFFFFFFFFFFFEh
0x180030753  sub     rax, rcx
0x180030756  cmp     rax, 1
0x18003075a  jb      loc_180030C0D
0x180030760  cmp     qword ptr [rsi+18h], 7
0x180030765  jbe     short loc_18003076A
0x180030767  mov     rsi, [rsi]
0x18003076a  mov     [rsp+190h+pBuffer], 1; __int64
0x180030773  lea     rax, asc_1800B1B48; "."
0x18003077a  mov     [rsp+190h+pPropertySize], rax; Src
0x18003077f  mov     [rsp+190h+pPropertyData], rcx; __int64
0x180030784  mov     r9, rsi
0x180030787  lea     rcx, [rbp+90h+var_C0]; void *
0x18003078b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180030790  nop
0x180030791  mov     [rsp+190h+var_150], 16h
0x180030799  lea     r8, [rbp+90h+var_100]
0x18003079d  lea     rdx, [rbp+90h+var_C0]
0x1800307a1  lea     rcx, [rbp+90h+var_E0]
0x1800307a5  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x1800307aa  mov     esi, 1Eh
0x1800307af  xorps   xmm0, xmm0
0x1800307b2  movups  xmmword ptr [rbp+90h+var_98], xmm0
0x1800307b6  mov     qword ptr [rbp+90h+var_88], rbx
0x1800307ba  mov     qword ptr [rbp+90h+var_88+8], rbx
0x1800307be  movups  xmm0, xmmword ptr [rax]
0x1800307c1  movups  xmmword ptr [rbp+90h+var_98], xmm0
0x1800307c5  movups  xmm1, xmmword ptr [rax+10h]
0x1800307c9  movups  [rbp+90h+var_88], xmm1
0x1800307cd  mov     [rax], bx
0x1800307d0  mov     [rax+10h], rbx
0x1800307d4  mov     qword ptr [rax+18h], 7
0x1800307dc  test    sil, 8
0x1800307e0  jz      short loc_1800307EF
0x1800307e2  and     esi, 0FFFFFFF7h
0x1800307e5  lea     rcx, [rbp+90h+var_E0]
0x1800307e9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800307ee  nop
0x1800307ef  test    sil, 4
0x1800307f3  jz      short loc_180030802
0x1800307f5  and     esi, 0FFFFFFFBh
0x1800307f8  lea     rcx, [rbp+90h+var_C0]
0x1800307fc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180030801  nop
0x180030802  test    dil, sil
0x180030805  jz      short loc_180030814
0x180030807  and     esi, 0FFFFFFFDh
0x18003080a  lea     rcx, [rbp+90h+var_100]
0x18003080e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180030813  nop
0x180030814  test    sil, 1
0x180030818  jz      short loc_180030824
0x18003081a  lea     rcx, [rsp+190h+var_140]
0x18003081f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180030824  mov     [rsp+190h+var_140.Reserved], ebx
0x180030828  mov     [rsp+190h+var_140.PropertyName], r12
0x18003082d  mov     [rsp+190h+var_140.ArrayIndex], 0FFFFFFFFh
0x180030835  mov     rdx, [r15+8]
0x180030839  cmp     rdx, [r15+10h]
0x18003083d  jz      short loc_18003084F
0x18003083f  movups  xmm0, xmmword ptr [rsp+190h+var_140.PropertyName]
0x180030844  movdqu  xmmword ptr [rdx], xmm0
0x180030848  add     qword ptr [r15+8], 10h
0x18003084d  jmp     short loc_18003085C
0x18003084f  lea     r8, [rsp+190h+var_140]
0x180030854  mov     rcx, r15
0x180030857  call    ??$_Emplace_reallocate@AEBU_PROPERTY_DATA_DESCRIPTOR@@@?$vector@U_PROPERTY_DATA_DESCRIPTOR@@V?$allocator@U_PROPERTY_DATA_DESCRIPTOR@@@std@@@std@@AEAAPEAU_PROPERTY_DATA_DESCRIPTOR@@QEAU2@AEBU2@@Z; std::vector<_PROPERTY_DATA_DESCRIPTOR>::_Emplace_reallocate<_PROPERTY_DATA_DESCRIPTOR const &>(_PROPERTY_DATA_DESCRIPTOR * const,_PROPERTY_DATA_DESCRIPTOR const &)
0x18003085c  mov     qword ptr [rbp+90h+var_100], r15
0x180030860  mov     byte ptr [rbp+90h+var_100+8], 1
0x180030864  test    byte ptr [r13+70h], 1
0x180030869  jz      loc_180030914
0x18003086f  mov     eax, [rbp+90h+arg_28]
0x180030875  test    eax, eax
0x180030877  jnz     short loc_1800308BD
0x180030879  lea     rax, [rbp+90h+var_98]
0x18003087d  cmp     qword ptr [rbp+90h+var_88+8], 7
0x180030882  cmova   rax, [rbp+90h+var_98]
0x180030887  mov     rcx, [rbp+98h]; this
0x18003088e  mov     [rsp+190h+pPropertySize], rax; char *
0x180030893  lea     rax, aMaxStructDepth; "Max struct depth reached, skipping: %ls"
0x18003089a  mov     [rsp+190h+pPropertyData], rax; int
0x18003089f  mov     ebx, 8000000Bh
0x1800308a4  mov     r9d, ebx; char *
0x1800308a7  lea     r8, aCW1SSrcCalliop_5; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x1800308ae  mov     edx, 2DEh; void *
0x1800308b3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800308b8  jmp     loc_180030BDF
0x1800308bd  movzx   ecx, word ptr [r13+78h]
0x1800308c2  movzx   esi, word ptr [r13+7Ah]
0x1800308c7  mov     edi, ebx
0x1800308c9  test    esi, esi
0x1800308cb  jz      loc_180030BDF
0x1800308d1  lea     r12d, [rax-1]
0x1800308d5  mov     ebx, ecx
0x1800308d7  mov     r13, [rbp+90h+var_110]
0x1800308db  lea     r8d, [rdi+rbx]
0x1800308df  lea     rax, [rbp+90h+var_98]
0x1800308e3  mov     [rsp+190h+pBuffer], rax
0x1800308e8  mov     dword ptr [rsp+190h+pPropertySize], r12d
0x1800308ed  mov     rax, [rsp+190h+var_118]
0x1800308f2  mov     [rsp+190h+pPropertyData], rax
0x1800308f7  mov     r9, r15
0x1800308fa  mov     rdx, r13
0x1800308fd  mov     rcx, [rsp+190h+pEvent]
0x180030902  call    ?ExtractProperty@EtwFileProcessor@Diagnostics@@CAJPEAU_EVENT_RECORD@@PEAU_TRACE_EVENT_INFO@@KAEAV?$vector@U_PROPERTY_DATA_DESCRIPTOR@@V?$allocator@U_PROPERTY_DATA_DESCRIPTOR@@@std@@@std@@AEAVOTelLogRecord@2@KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@6@@Z; Diagnostics::EtwFileProcessor::ExtractProperty(_EVENT_RECORD *,_TRACE_EVENT_INFO *,ulong,std::vector<_PROPERTY_DATA_DESCRIPTOR> &,Diagnostics::OTelLogRecord &,ulong,std::wstring const &)
0x180030907  inc     edi
0x180030909  cmp     edi, esi
0x18003090b  jb      short loc_1800308DB
0x18003090d  xor     ebx, ebx
0x18003090f  jmp     loc_180030BDF
0x180030914  mov     rax, [r15]
0x180030917  mov     rsi, [r15+8]
0x18003091b  sub     rsi, rax
0x18003091e  sar     rsi, 4
0x180030922  mov     [rbp+90h+BufferSize], ebx
0x180030925  lea     rcx, [rbp+90h+BufferSize]
0x180030929  mov     [rsp+190h+pPropertySize], rcx; pPropertySize
0x18003092e  mov     [rsp+190h+pPropertyData], rax; pPropertyData
0x180030933  mov     r9d, esi; PropertyDataCount
0x180030936  xor     r8d, r8d; pTdhContext
0x180030939  xor     edx, edx; TdhContextCount
0x18003093b  mov     r12, [rsp+190h+pEvent]
0x180030940  mov     rcx, r12; pEvent
0x180030943  call    cs:__imp_TdhGetPropertySize
0x180030949  mov     r9d, eax; char *
0x18003094c  test    eax, eax
0x18003094e  jz      short loc_18003098E
0x180030950  lea     rax, [rbp+90h+var_98]
0x180030954  cmp     qword ptr [rbp+90h+var_88+8], 7
0x180030959  cmova   rax, [rbp+90h+var_98]
0x18003095e  mov     rcx, [rbp+98h]; this
0x180030965  mov     [rsp+190h+pPropertySize], rax; char *
0x18003096a  lea     rax, aTdhgetproperty_0; "TdhGetPropertySize failed for: %ls"
0x180030971  mov     [rsp+190h+pPropertyData], rax; unsigned int
0x180030976  lea     r8, aCW1SSrcCalliop_5; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x18003097d  mov     edx, 2F0h; void *
0x180030982  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180030987  mov     ebx, eax
0x180030989  jmp     loc_180030BDF
0x18003098e  cmp     [rbp+90h+BufferSize], ebx
0x180030991  jz      loc_180030BDF
0x180030997  xorps   xmm0, xmm0
0x18003099a  xor     eax, eax
0x18003099c  movups  xmmword ptr [rbp+90h+var_58], xmm0
0x1800309a0  mov     [rbp+90h+var_48], rax
0x1800309a4  mov     edx, [rbp+90h+BufferSize]
0x1800309a7  lea     rcx, [rbp+90h+var_58]
0x1800309ab  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800309b0  nop
0x1800309b1  mov     rax, [rbp+90h+var_58]
0x1800309b5  mov     edx, [rbp+90h+BufferSize]
0x1800309b8  mov     [rsp+190h+pBuffer], rax; pBuffer
0x1800309bd  mov     dword ptr [rsp+190h+pPropertySize], edx; BufferSize
0x1800309c1  mov     rax, [r15]
0x1800309c4  mov     [rsp+190h+pPropertyData], rax; pPropertyData
0x1800309c9  mov     r9d, esi; PropertyDataCount
0x1800309cc  xor     r8d, r8d; pTdhContext
0x1800309cf  xor     edx, edx; TdhContextCount
0x1800309d1  mov     rcx, r12; pEvent
0x1800309d4  call    cs:__imp_TdhGetProperty
0x1800309da  test    eax, eax
0x1800309dc  jz      short loc_180030A1F
0x1800309de  lea     rdx, [rbp+90h+var_98]
0x1800309e2  cmp     qword ptr [rbp+90h+var_88+8], 7
0x1800309e7  cmova   rdx, [rbp+90h+var_98]
0x1800309ec  mov     rcx, [rbp+98h]; this
0x1800309f3  mov     [rsp+190h+pPropertySize], rdx; char *
0x1800309f8  lea     rdx, aTdhgetproperty; "TdhGetProperty failed for: %ls"
0x1800309ff  mov     [rsp+190h+pPropertyData], rdx; unsigned int
0x180030a04  mov     r9d, eax; char *
0x180030a07  lea     r8, aCW1SSrcCalliop_5; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x180030a0e  mov     edx, 2F9h; void *
0x180030a13  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180030a18  mov     ebx, eax
0x180030a1a  jmp     loc_180030BD5
0x180030a1f  xorps   xmm0, xmm0
0x180030a22  movups  [rbp+90h+Src], xmm0
0x180030a26  mov     qword ptr [rbp+90h+var_68], rbx
0x180030a2a  mov     esi, 7
0x180030a2f  mov     qword ptr [rbp+90h+var_68+8], rsi
0x180030a33  mov     word ptr [rbp+90h+Src], bx
0x180030a37  movzx   ecx, word ptr [r13+78h]
0x180030a3c  cmp     ecx, 9
0x180030a3f  ja      short loc_180030A68
0x180030a41  jz      short loc_180030A92
0x180030a43  sub     ecx, 3
0x180030a46  jz      short loc_180030A8B
0x180030a48  sub     ecx, 1
0x180030a4b  jz      short loc_180030A8B
0x180030a4d  sub     ecx, 1
0x180030a50  jz      short loc_180030A97
0x180030a52  sub     ecx, 1
0x180030a55  jz      short loc_180030A97
0x180030a57  sub     ecx, 1
0x180030a5a  jz      short loc_180030A61
0x180030a5c  cmp     ecx, 1
0x180030a5f  jnz     short loc_180030A80
0x180030a61  mov     edi, 4
0x180030a66  jmp     short loc_180030A97
0x180030a68  sub     ecx, 0Ah
0x180030a6b  jz      short loc_180030A92
0x180030a6d  sub     ecx, 1
0x180030a70  jz      short loc_180030A61
0x180030a72  sub     ecx, 1
0x180030a75  jz      short loc_180030A92
0x180030a77  sub     ecx, 1
0x180030a7a  jz      short loc_180030A8B
0x180030a7c  cmp     ecx, edi
0x180030a7e  jz      short loc_180030A84
0x180030a80  mov     edi, ebx
0x180030a82  jmp     short loc_180030A97
0x180030a84  mov     edi, 10h
0x180030a89  jmp     short loc_180030A97
0x180030a8b  mov     edi, 1
0x180030a90  jmp     short loc_180030A97
0x180030a92  mov     edi, 8
0x180030a97  mov     r9d, [rbp+90h+BufferSize]
0x180030a9b  test    byte ptr [r13+70h], 6
0x180030aa0  jz      loc_180030B26
0x180030aa6  test    edi, edi
0x180030aa8  jz      short loc_180030B26
0x180030aaa  cmp     r9d, edi
0x180030aad  jbe     short loc_180030B26
0x180030aaf  xor     edx, edx
0x180030ab1  mov     eax, r9d
0x180030ab4  div     edi
0x180030ab6  mov     r12d, eax
0x180030ab9  mov     esi, ebx
0x180030abb  test    eax, eax
0x180030abd  jz      loc_180030B6F
0x180030ac3  test    esi, esi
0x180030ac5  jz      short loc_180030ADD
0x180030ac7  mov     r8d, 1
0x180030acd  lea     rdx, asc_1800AA2E0; "|"
0x180030ad4  lea     rcx, [rbp+90h+Src]; Src
0x180030ad8  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180030add  mov     r8d, edi
0x180030ae0  imul    r8d, esi
0x180030ae4  add     r8, [rbp+90h+var_58]
0x180030ae8  mov     r9d, edi
0x180030aeb  lea     rdx, [r13+70h]
0x180030aef  lea     rcx, [rbp+90h+var_E0]
0x180030af3  call    ?FormatPropertyValue@EtwFileProcessor@Diagnostics@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_EVENT_PROPERTY_INFO@@PEBEK@Z; Diagnostics::EtwFileProcessor::FormatPropertyValue(_EVENT_PROPERTY_INFO const &,uchar const *,ulong)
0x180030af8  nop
0x180030af9  mov     r8, [rax+10h]
0x180030afd  cmp     qword ptr [rax+18h], 7
0x180030b02  jbe     short loc_180030B07
  ... truncated ...
```
