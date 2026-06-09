# IASService::get_LogRejectedRequests(int *)

- ea: `0x180033230`
- end: `0x18003334b`
- name: `?get_LogRejectedRequests@IASService@@UEAAJPEAH@Z`
- size: `283`
- prototype: `__int64 __fastcall(IASService *__hidden this, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180027ee4`
- `0x18002cd00`
- `0x18002f240`
- `0x1800325c0`
- `0x180033230`
- `0x180042a80`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003324a`
- `OLEAUT32!__imp_VariantInit` at `0x18003324a`

## pseudocode

```c
__int64 __fastcall IASService::get_LogRejectedRequests(struct ISdo **this, int *a2)
{
  int SdoProperty; // ebx
  int v5; // edx
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF

  VariantInit(&pvarg);
  if ( this[22] || (SdoProperty = IASService::GetNTEventLogObject(this), SdoProperty >= 0) )
  {
    SdoProperty = GetSdoProperty(this[22], 0x403u, &pvarg);
    if ( SdoProperty >= 0 )
    {
      *a2 = pvarg.iVal == 0xFFFF;
      goto LABEL_14;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("GetSdoProperty(PROPERTY_EVENTLOG_LOG_MALFORMED) failed with 0x%x");
      v5 = 36;
      goto LABEL_7;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("GetNTEventLogObject failed with 0x%x");
    v5 = 35;
LABEL_7:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids,
      (unsigned int)"NPSSDO",
      SdoProperty);
  }
LABEL_14:
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  return (unsigned int)SdoProperty;
}

```

## disassembly

```asm
0x180033230  mov     [rsp+arg_0], rbx
0x180033235  mov     [rsp+arg_8], rsi
0x18003323a  push    rdi
0x18003323b  sub     rsp, 50h
0x18003323f  mov     rdi, rcx
0x180033242  mov     rsi, rdx
0x180033245  lea     rcx, [rsp+58h+pvarg]; pvarg
0x18003324a  call    cs:__imp_VariantInit
0x180033250  cmp     qword ptr [rdi+0B0h], 0
0x180033258  jnz     short loc_1800332CD
0x18003325a  mov     rcx, rdi; this
0x18003325d  call    ?GetNTEventLogObject@IASService@@QEAAJXZ; IASService::GetNTEventLogObject(void)
0x180033262  mov     ebx, eax
0x180033264  test    eax, eax
0x180033266  jns     short loc_1800332CD
0x180033268  mov     rax, cs:WPP_GLOBAL_Control
0x18003326f  lea     rcx, WPP_GLOBAL_Control
0x180033276  cmp     rax, rcx
0x180033279  jz      loc_18003332F
0x18003327f  cmp     byte ptr [rax+19h], 2
0x180033283  jb      loc_18003332F
0x180033289  test    dword ptr [rax+1Ch], 400h
0x180033290  jz      loc_18003332F
0x180033296  mov     edx, ebx
0x180033298  lea     rcx, aGetnteventlogo; "GetNTEventLogObject failed with 0x%x"
0x18003329f  call    WppDbgPrint
0x1800332a4  mov     edx, 23h ; '#'
0x1800332a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800332b0  lea     r9, aNpssdo; "NPSSDO"
0x1800332b7  lea     r8, WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids
0x1800332be  mov     [rsp+58h+var_38], ebx
0x1800332c2  mov     rcx, [rcx+10h]
0x1800332c6  call    WPP_SF_sd
0x1800332cb  jmp     short loc_18003332F
0x1800332cd  mov     rcx, [rdi+0B0h]; struct ISdo *
0x1800332d4  lea     r8, [rsp+58h+pvarg]; struct tagVARIANT *
0x1800332d9  mov     edx, 403h; unsigned int
0x1800332de  call    ?GetSdoProperty@@YAJPEAUISdo@@KPEAUtagVARIANT@@@Z; GetSdoProperty(ISdo *,ulong,tagVARIANT *)
0x1800332e3  mov     ebx, eax
0x1800332e5  test    eax, eax
0x1800332e7  jns     short loc_180033320
0x1800332e9  mov     rax, cs:WPP_GLOBAL_Control
0x1800332f0  lea     rcx, WPP_GLOBAL_Control
0x1800332f7  cmp     rax, rcx
0x1800332fa  jz      short loc_18003332F
0x1800332fc  cmp     byte ptr [rax+19h], 2
0x180033300  jb      short loc_18003332F
0x180033302  test    dword ptr [rax+1Ch], 400h
0x180033309  jz      short loc_18003332F
0x18003330b  mov     edx, ebx
0x18003330d  lea     rcx, aGetsdoproperty_0; "GetSdoProperty(PROPERTY_EVENTLOG_LOG_MA"...
0x180033314  call    WppDbgPrint
0x180033319  mov     edx, 24h ; '$'
0x18003331e  jmp     short loc_1800332A9
0x180033320  xor     eax, eax
0x180033322  or      ecx, 0FFFFFFFFh
0x180033325  cmp     cx, word ptr [rsp+58h+pvarg+8]
0x18003332a  setz    al
0x18003332d  mov     [rsi], eax
0x18003332f  lea     rcx, [rsp+58h+pvarg]; this
0x180033334  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180033339  mov     rsi, [rsp+58h+arg_8]
0x18003333e  mov     eax, ebx
0x180033340  mov     rbx, [rsp+58h+arg_0]
0x180033345  add     rsp, 50h
0x180033349  pop     rdi
0x18003334a  retn
```
