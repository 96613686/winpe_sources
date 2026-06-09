# SessionDataUtil::WUOptionalSessionInfo::Initialize(ulong,void const *,ulong,IUnknown *)

- ea: `0x14001601c`
- end: `0x140016312`
- name: `?Initialize@WUOptionalSessionInfo@SessionDataUtil@@AEAAJKPEBXKPEAUIUnknown@@@Z`
- size: `758`
- prototype: `__int64 __usercall@<rax>(wchar_t *this@<rcx>, unsigned int@<edx>, const void *@<r8>, unsigned int@<r9d>, struct IUnknown *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x140015c4c`

## callees

- `0x140002ac0`
- `0x14000d4cc`
- `0x140015d84`
- `0x140015dec`
- `0x14001601c`
- `0x1400183a0`
- `0x140018528`
- `0x14001aa60`
- `0x1400206e0`

## string_xrefs

- `0x14001616e`: `UpdateId`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall SessionDataUtil::WUOptionalSessionInfo::Initialize(
        wchar_t *this,
        unsigned int a2,
        const wchar_t **a3,
        int a4,
        struct IUnknown *a5)
{
  int inited; // edi
  __int64 v11; // rdx
  struct IUnknownVtbl *lpVtbl; // rax
  __int64 v13; // rdx
  wchar_t *v14; // rsi
  void *v15; // rcx
  wchar_t *v16; // rsi
  void *v17; // rcx
  wchar_t *v18; // rsi
  void *v19; // rcx
  wchar_t *v20; // rsi
  void *v21; // rcx
  wchar_t *v22; // rsi
  void *v23; // rcx
  wchar_t **v24; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)0x80070057LL,
      (int)v24);
    return 2147942487LL;
  }
  inited = SessionDataUtil::WUOptionalSessionInfo::Initialize((SessionDataUtil::WUOptionalSessionInfo *)this, a2, a3);
  if ( inited < 0 )
  {
    v11 = 283;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)(unsigned int)inited,
      (int)v24);
    return (unsigned int)inited;
  }
  inited = SessionDataUtil::WUOptionalSessionInfo::InitOptionalSessionInfo(
             (SessionDataUtil::WUOptionalSessionInfo *)this,
             *((void **)this + 6));
  if ( inited < 0 )
  {
    v11 = 284;
    goto LABEL_5;
  }
  if ( a2 && a5 && a4 )
  {
    lpVtbl = a5->lpVtbl;
    v24 = 0;
    inited = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, wchar_t ***))lpVtbl->QueryInterface)(
               a5,
               &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3,
               &v24);
    if ( inited >= 0 )
    {
      if ( *(_QWORD *)this )
      {
        SusFree(*(void **)this);
        *(_QWORD *)this = 0;
      }
      inited = JsonUtil::GetStringPropertyWithDefault(
                 (JsonUtil *)v24,
                 (struct ABI::Windows::Data::Json::IJsonObject *)L"SessionData",
                 *a3,
                 this);
      if ( inited >= 0 )
      {
        **((_QWORD **)this + 6) = *(_QWORD *)this;
        v14 = this + 4;
        v15 = (void *)*((_QWORD *)this + 1);
        if ( v15 )
        {
          SusFree(v15);
          *(_QWORD *)v14 = 0;
        }
        inited = JsonUtil::GetStringPropertyWithDefault(
                   (JsonUtil *)v24,
                   (struct ABI::Windows::Data::Json::IJsonObject *)L"UpdateId",
                   a3[1],
                   this + 4);
        if ( inited >= 0 )
        {
          *(_QWORD *)(*((_QWORD *)this + 6) + 8LL) = *(_QWORD *)v14;
          v16 = this + 8;
          v17 = (void *)*((_QWORD *)this + 2);
          if ( v17 )
          {
            SusFree(v17);
            *(_QWORD *)v16 = 0;
          }
          inited = JsonUtil::GetStringPropertyWithDefault(
                     (JsonUtil *)v24,
                     (struct ABI::Windows::Data::Json::IJsonObject *)L"FlightId",
                     a3[2],
                     this + 8);
          if ( inited >= 0 )
          {
            *(_QWORD *)(*((_QWORD *)this + 6) + 16LL) = *(_QWORD *)v16;
            v18 = this + 12;
            v19 = (void *)*((_QWORD *)this + 3);
            if ( v19 )
            {
              SusFree(v19);
              *(_QWORD *)v18 = 0;
            }
            inited = JsonUtil::GetStringPropertyWithDefault(
                       (JsonUtil *)v24,
                       (struct ABI::Windows::Data::Json::IJsonObject *)L"FlightMetadata",
                       a3[3],
                       this + 12);
            if ( inited >= 0 )
            {
              *(_QWORD *)(*((_QWORD *)this + 6) + 24LL) = *(_QWORD *)v18;
              v20 = this + 16;
              v21 = (void *)*((_QWORD *)this + 4);
              if ( v21 )
              {
                SusFree(v21);
                *(_QWORD *)v20 = 0;
              }
              inited = JsonUtil::GetStringPropertyWithDefault(
                         (JsonUtil *)v24,
                         (struct ABI::Windows::Data::Json::IJsonObject *)L"CorrelationVector",
                         (wchar_t *)a3[4],
                         (char *)this + 32);
              if ( inited >= 0 )
              {
                *(_QWORD *)(*((_QWORD *)this + 6) + 32LL) = *(_QWORD *)v20;
                v22 = this + 20;
                v23 = (void *)*((_QWORD *)this + 5);
                if ( v23 )
                {
                  SusFree(v23);
                  *(_QWORD *)v22 = 0;
                }
                inited = JsonUtil::GetStringPropertyWithDefault(
                           (JsonUtil *)v24,
                           (struct ABI::Windows::Data::Json::IJsonObject *)L"RelatedCV",
                           (wchar_t *)a3[5],
                           (char *)this + 40);
                if ( inited >= 0 )
                {
                  *(_QWORD *)(*((_QWORD *)this + 6) + 40LL) = *(_QWORD *)v22;
                  inited = 0;
LABEL_40:
                  if ( v24 )
                    (*((void (__fastcall **)(wchar_t **))*v24 + 2))(v24);
                  return (unsigned int)inited;
                }
                v13 = 327;
              }
              else
              {
                v13 = 321;
              }
            }
            else
            {
              v13 = 315;
            }
          }
          else
          {
            v13 = 309;
          }
        }
        else
        {
          v13 = 303;
        }
      }
      else
      {
        v13 = 297;
      }
    }
    else
    {
      v13 = 290;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)(unsigned int)inited,
      (int)v24);
    goto LABEL_40;
  }
  return 0;
}

```

## disassembly

```asm
0x14001601c  mov     [rsp+arg_18], rbx
0x140016021  push    rbp
0x140016022  push    rsi
0x140016023  push    rdi
0x140016024  push    r14
0x140016026  push    r15
0x140016028  sub     rsp, 30h
0x14001602c  mov     rax, cs:__security_cookie
0x140016033  xor     rax, rsp
0x140016036  mov     [rsp+58h+var_30], rax
0x14001603b  mov     ebp, r9d
0x14001603e  mov     r14, r8
0x140016041  mov     esi, edx
0x140016043  mov     rbx, rcx
0x140016046  mov     r15, [rsp+58h+arg_20]
0x14001604e  test    r8, r8
0x140016051  jnz     short loc_140016078
0x140016053  mov     rcx, [rsp+58h]; this
0x140016058  mov     ebx, 80070057h
0x14001605d  mov     r9d, ebx; char *
0x140016060  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140016067  mov     edx, 119h; void *
0x14001606c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016071  mov     eax, ebx
0x140016073  jmp     loc_1400162F4
0x140016078  call    ?Initialize@WUOptionalSessionInfo@SessionDataUtil@@AEAAJKPEBX@Z; SessionDataUtil::WUOptionalSessionInfo::Initialize(ulong,void const *)
0x14001607d  mov     edi, eax
0x14001607f  test    eax, eax
0x140016081  jns     short loc_1400160A3
0x140016083  mov     edx, 11Bh; void *
0x140016088  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14001608f  mov     r9d, edi; char *
0x140016092  mov     rcx, [rsp+58h]; this
0x140016097  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001609c  mov     eax, edi
0x14001609e  jmp     loc_1400162F4
0x1400160a3  mov     rdx, [rbx+30h]; void *
0x1400160a7  mov     rcx, rbx; this
0x1400160aa  call    ?InitOptionalSessionInfo@WUOptionalSessionInfo@SessionDataUtil@@QEAAJPEAX@Z; SessionDataUtil::WUOptionalSessionInfo::InitOptionalSessionInfo(void *)
0x1400160af  mov     edi, eax
0x1400160b1  test    eax, eax
0x1400160b3  jns     short loc_1400160BC
0x1400160b5  mov     edx, 11Ch
0x1400160ba  jmp     short loc_140016088
0x1400160bc  cmp     esi, 1
0x1400160bf  jb      loc_1400162F2
0x1400160c5  test    r15, r15
0x1400160c8  jz      loc_1400162F2
0x1400160ce  cmp     ebp, 1
0x1400160d1  jb      loc_1400162F2
0x1400160d7  mov     rax, [r15]
0x1400160da  mov     [rsp+58h+var_38], 0; int
0x1400160e3  lea     r8, [rsp+58h+var_38]
0x1400160e8  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x1400160ef  mov     rcx, r15
0x1400160f2  mov     rax, [rax]
0x1400160f5  call    _guard_dispatch_icall
0x1400160fa  mov     edi, eax
0x1400160fc  test    eax, eax
0x1400160fe  jns     short loc_14001610A
0x140016100  mov     edx, 122h
0x140016105  jmp     loc_1400162B3
0x14001610a  mov     rcx, [rbx]; lpMem
0x14001610d  test    rcx, rcx
0x140016110  jz      short loc_14001611E
0x140016112  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140016117  mov     qword ptr [rbx], 0
0x14001611e  mov     r9, rbx; wchar_t *
0x140016121  mov     r8, [r14]; wchar_t *
0x140016124  lea     rdx, aSessiondata; "SessionData"
0x14001612b  mov     rcx, [rsp+58h+var_38]; this
0x140016130  call    ?GetStringPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_W1PEAPEA_W@Z; JsonUtil::GetStringPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,wchar_t const *,wchar_t * *)
0x140016135  mov     edi, eax
0x140016137  test    eax, eax
0x140016139  jns     short loc_140016145
0x14001613b  mov     edx, 129h
0x140016140  jmp     loc_1400162B3
0x140016145  mov     rcx, [rbx+30h]
0x140016149  mov     rax, [rbx]
0x14001614c  mov     [rcx], rax
0x14001614f  lea     rsi, [rbx+8]
0x140016153  mov     rcx, [rsi]; lpMem
0x140016156  test    rcx, rcx
0x140016159  jz      short loc_140016167
0x14001615b  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140016160  mov     qword ptr [rsi], 0
0x140016167  mov     r9, rsi; wchar_t *
0x14001616a  mov     r8, [r14+8]; wchar_t *
0x14001616e  lea     rdx, aUpdateid; "UpdateId"
0x140016175  mov     rcx, [rsp+58h+var_38]; this
0x14001617a  call    ?GetStringPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_W1PEAPEA_W@Z; JsonUtil::GetStringPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,wchar_t const *,wchar_t * *)
0x14001617f  mov     edi, eax
0x140016181  test    eax, eax
0x140016183  jns     short loc_14001618F
0x140016185  mov     edx, 12Fh
0x14001618a  jmp     loc_1400162B3
0x14001618f  mov     rcx, [rbx+30h]
0x140016193  mov     rax, [rsi]
0x140016196  mov     [rcx+8], rax
0x14001619a  lea     rsi, [rbx+10h]
0x14001619e  mov     rcx, [rsi]; lpMem
0x1400161a1  test    rcx, rcx
0x1400161a4  jz      short loc_1400161B2
0x1400161a6  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400161ab  mov     qword ptr [rsi], 0
0x1400161b2  mov     r9, rsi; wchar_t *
0x1400161b5  mov     r8, [r14+10h]; wchar_t *
0x1400161b9  lea     rdx, aFlightid; "FlightId"
0x1400161c0  mov     rcx, [rsp+58h+var_38]; this
0x1400161c5  call    ?GetStringPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_W1PEAPEA_W@Z; JsonUtil::GetStringPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,wchar_t const *,wchar_t * *)
0x1400161ca  mov     edi, eax
0x1400161cc  test    eax, eax
0x1400161ce  jns     short loc_1400161DA
0x1400161d0  mov     edx, 135h
0x1400161d5  jmp     loc_1400162B3
0x1400161da  mov     rcx, [rbx+30h]
0x1400161de  mov     rax, [rsi]
0x1400161e1  mov     [rcx+10h], rax
0x1400161e5  lea     rsi, [rbx+18h]
0x1400161e9  mov     rcx, [rsi]; lpMem
0x1400161ec  test    rcx, rcx
0x1400161ef  jz      short loc_1400161FD
0x1400161f1  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400161f6  mov     qword ptr [rsi], 0
0x1400161fd  mov     r9, rsi; wchar_t *
0x140016200  mov     r8, [r14+18h]; wchar_t *
0x140016204  lea     rdx, aFlightmetadata; "FlightMetadata"
0x14001620b  mov     rcx, [rsp+58h+var_38]; this
0x140016210  call    ?GetStringPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_W1PEAPEA_W@Z; JsonUtil::GetStringPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,wchar_t const *,wchar_t * *)
0x140016215  mov     edi, eax
0x140016217  test    eax, eax
0x140016219  jns     short loc_140016225
0x14001621b  mov     edx, 13Bh
0x140016220  jmp     loc_1400162B3
0x140016225  mov     rcx, [rbx+30h]
0x140016229  mov     rax, [rsi]
0x14001622c  mov     [rcx+18h], rax
0x140016230  lea     rsi, [rbx+20h]
0x140016234  mov     rcx, [rsi]; lpMem
0x140016237  test    rcx, rcx
0x14001623a  jz      short loc_140016248
0x14001623c  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140016241  mov     qword ptr [rsi], 0
0x140016248  mov     r9, rsi; char *
0x14001624b  mov     r8, [r14+20h]; wchar_t *
0x14001624f  lea     rdx, aCorrelationvec; "CorrelationVector"
0x140016256  mov     rcx, [rsp+58h+var_38]; this
0x14001625b  call    ?GetStringPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WPEBDPEAPEAD@Z; JsonUtil::GetStringPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,char const *,char * *)
0x140016260  mov     edi, eax
0x140016262  test    eax, eax
0x140016264  jns     short loc_14001626D
0x140016266  mov     edx, 141h
0x14001626b  jmp     short loc_1400162B3
0x14001626d  mov     rcx, [rbx+30h]
0x140016271  mov     rax, [rsi]
0x140016274  mov     [rcx+20h], rax
0x140016278  lea     rsi, [rbx+28h]
0x14001627c  mov     rcx, [rsi]; lpMem
0x14001627f  test    rcx, rcx
0x140016282  jz      short loc_140016290
0x140016284  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140016289  mov     qword ptr [rsi], 0
0x140016290  mov     r9, rsi; char *
0x140016293  mov     r8, [r14+28h]; wchar_t *
0x140016297  lea     rdx, aRelatedcv; "RelatedCV"
0x14001629e  mov     rcx, [rsp+58h+var_38]; this
0x1400162a3  call    ?GetStringPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WPEBDPEAPEAD@Z; JsonUtil::GetStringPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,char const *,char * *)
0x1400162a8  mov     edi, eax
0x1400162aa  test    eax, eax
0x1400162ac  jns     short loc_1400162C9
0x1400162ae  mov     edx, 147h; void *
0x1400162b3  mov     rcx, [rsp+58h]; this
0x1400162b8  mov     r9d, edi; char *
0x1400162bb  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400162c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400162c7  jmp     short loc_1400162D6
0x1400162c9  mov     rcx, [rbx+30h]
0x1400162cd  mov     rax, [rsi]
0x1400162d0  mov     [rcx+28h], rax
0x1400162d4  xor     edi, edi
0x1400162d6  mov     rcx, [rsp+58h+var_38]
0x1400162db  test    rcx, rcx
0x1400162de  jz      short loc_1400162ED
0x1400162e0  mov     rdx, [rcx]
0x1400162e3  mov     rax, [rdx+10h]
0x1400162e7  call    _guard_dispatch_icall
0x1400162ec  nop
0x1400162ed  jmp     loc_14001609C
0x1400162f2  xor     eax, eax
0x1400162f4  mov     rcx, [rsp+58h+var_30]
0x1400162f9  xor     rcx, rsp; StackCookie
0x1400162fc  call    __security_check_cookie
0x140016301  mov     rbx, [rsp+58h+arg_18]
0x140016306  add     rsp, 30h
0x14001630a  pop     r15
0x14001630c  pop     r14
0x14001630e  pop     rdi
0x14001630f  pop     rsi
0x140016310  pop     rbp
0x140016311  retn
```
