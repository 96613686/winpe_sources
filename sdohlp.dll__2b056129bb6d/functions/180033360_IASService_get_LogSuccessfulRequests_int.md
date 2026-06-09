# IASService::get_LogSuccessfulRequests(int *)

- ea: `0x180033360`
- end: `0x18003347b`
- name: `?get_LogSuccessfulRequests@IASService@@UEAAJPEAH@Z`
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
- `0x180033360`
- `0x180042a80`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003337a`
- `OLEAUT32!__imp_VariantInit` at `0x18003337a`

## pseudocode

```c
__int64 __fastcall IASService::get_LogSuccessfulRequests(struct ISdo **this, int *a2)
{
  int SdoProperty; // ebx
  int v5; // edx
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF

  VariantInit(&pvarg);
  if ( this[22] || (SdoProperty = IASService::GetNTEventLogObject(this), SdoProperty >= 0) )
  {
    SdoProperty = GetSdoProperty(this[22], 0x404u, &pvarg);
    if ( SdoProperty >= 0 )
    {
      *a2 = pvarg.iVal == 0xFFFF;
      goto LABEL_14;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("GetSdoProperty(PROPERTY_EVENTLOG_LOG_DEBUG) failed with 0x%x");
      v5 = 32;
      goto LABEL_7;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("GetNTEventLogObject failed with 0x%x");
    v5 = 31;
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
0x180033360  mov     [rsp+arg_0], rbx
0x180033365  mov     [rsp+arg_8], rsi
0x18003336a  push    rdi
0x18003336b  sub     rsp, 50h
0x18003336f  mov     rdi, rcx
0x180033372  mov     rsi, rdx
0x180033375  lea     rcx, [rsp+58h+pvarg]; pvarg
0x18003337a  call    cs:__imp_VariantInit
0x180033380  cmp     qword ptr [rdi+0B0h], 0
0x180033388  jnz     short loc_1800333FD
0x18003338a  mov     rcx, rdi; this
0x18003338d  call    ?GetNTEventLogObject@IASService@@QEAAJXZ; IASService::GetNTEventLogObject(void)
0x180033392  mov     ebx, eax
0x180033394  test    eax, eax
0x180033396  jns     short loc_1800333FD
0x180033398  mov     rax, cs:WPP_GLOBAL_Control
0x18003339f  lea     rcx, WPP_GLOBAL_Control
0x1800333a6  cmp     rax, rcx
0x1800333a9  jz      loc_18003345F
0x1800333af  cmp     byte ptr [rax+19h], 2
0x1800333b3  jb      loc_18003345F
0x1800333b9  test    dword ptr [rax+1Ch], 400h
0x1800333c0  jz      loc_18003345F
0x1800333c6  mov     edx, ebx
0x1800333c8  lea     rcx, aGetnteventlogo; "GetNTEventLogObject failed with 0x%x"
0x1800333cf  call    WppDbgPrint
0x1800333d4  mov     edx, 1Fh
0x1800333d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800333e0  lea     r9, aNpssdo; "NPSSDO"
0x1800333e7  lea     r8, WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids
0x1800333ee  mov     [rsp+58h+var_38], ebx
0x1800333f2  mov     rcx, [rcx+10h]
0x1800333f6  call    WPP_SF_sd
0x1800333fb  jmp     short loc_18003345F
0x1800333fd  mov     rcx, [rdi+0B0h]; struct ISdo *
0x180033404  lea     r8, [rsp+58h+pvarg]; struct tagVARIANT *
0x180033409  mov     edx, 404h; unsigned int
0x18003340e  call    ?GetSdoProperty@@YAJPEAUISdo@@KPEAUtagVARIANT@@@Z; GetSdoProperty(ISdo *,ulong,tagVARIANT *)
0x180033413  mov     ebx, eax
0x180033415  test    eax, eax
0x180033417  jns     short loc_180033450
0x180033419  mov     rax, cs:WPP_GLOBAL_Control
0x180033420  lea     rcx, WPP_GLOBAL_Control
0x180033427  cmp     rax, rcx
0x18003342a  jz      short loc_18003345F
0x18003342c  cmp     byte ptr [rax+19h], 2
0x180033430  jb      short loc_18003345F
0x180033432  test    dword ptr [rax+1Ch], 400h
0x180033439  jz      short loc_18003345F
0x18003343b  mov     edx, ebx
0x18003343d  lea     rcx, aGetsdoproperty_5; "GetSdoProperty(PROPERTY_EVENTLOG_LOG_DE"...
0x180033444  call    WppDbgPrint
0x180033449  mov     edx, 20h ; ' '
0x18003344e  jmp     short loc_1800333D9
0x180033450  xor     eax, eax
0x180033452  or      ecx, 0FFFFFFFFh
0x180033455  cmp     cx, word ptr [rsp+58h+pvarg+8]
0x18003345a  setz    al
0x18003345d  mov     [rsi], eax
0x18003345f  lea     rcx, [rsp+58h+pvarg]; this
0x180033464  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180033469  mov     rsi, [rsp+58h+arg_8]
0x18003346e  mov     eax, ebx
0x180033470  mov     rbx, [rsp+58h+arg_0]
0x180033475  add     rsp, 50h
0x180033479  pop     rdi
0x18003347a  retn
```
