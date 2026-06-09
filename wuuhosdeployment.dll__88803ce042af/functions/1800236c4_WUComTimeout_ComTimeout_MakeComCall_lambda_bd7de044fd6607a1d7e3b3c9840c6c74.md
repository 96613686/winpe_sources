# WUComTimeout::ComTimeout::MakeComCall__lambda_bd7de044fd6607a1d7e3b3c9840c6c74___

- ea: `0x1800236c4`
- end: `0x180023855`
- name: `WUComTimeout::ComTimeout::MakeComCall__lambda_bd7de044fd6607a1d7e3b3c9840c6c74___`
- size: `401`
- prototype: `__int64 __fastcall(_QWORD **)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180022a8c`

## callees

- `0x180003950`
- `0x18000956c`
- `0x1800236c4`
- `0x1800316bc`
- `0x18003170c`
- `0x180031804`
- `0x180042630`
- `0x180049260`

## string_xrefs

- `0x1800237f4`: `COSDownloader::SetUpdatePriorityAttributeIfAvailable`
- `0x180023748`: `C:\__w\1\s\src\Client\inc\ComTimeout.h`
- `0x1800236f2`: `ComTimeout::MakeComCall [%hs]`
- `0x180023799`: `COM call timed out`
- `0x1800237d3`: `WUComTimeout::ComTimeout::MakeComCall`
- `0x180023805`: `COM call [%hs, from %hs:%u] timed out after %u seconds`

## pseudocode

```c
__int64 __fastcall WUComTimeout::ComTimeout::MakeComCall__lambda_bd7de044fd6607a1d7e3b3c9840c6c74___(_QWORD **a1)
{
  unsigned int v2; // edx
  int v3; // eax
  int v4; // ebx
  unsigned int v5; // edx
  unsigned int v6; // ecx
  __int128 pv; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  WUTrace(0, 0, 0x10000, 5);
  pv = 0;
  WORD6(pv) = 0;
  v3 = WUComTimeout::ComTimeout::SetTimer(&pv, v2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v4 = (*(__int64 (**)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, const wchar_t *, ...))(*(_QWORD *)(*a1)[17] + 40LL))(
           (*a1)[17],
           0,
           *a1[1],
           *a1[2],
           0,
           L"ComTimeout::MakeComCall [%hs]",
           "m_remoteDeploymentSession->SetAttributeInt(0 , attrName, attrValue)");
    if ( v4 < 0 && BYTE13(pv) )
    {
      WUTrace("WUComTimeout::ComTimeout::MakeComCall", 52, 32, 3);
      WUTelemetryAssertTriggered(v6, v5);
      WUTrace(0, 0, 0x10000, 1);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\ComTimeout.h",
      (const char *)(unsigned int)v3,
      0);
  }
  WUComTimeout::ComTimeout::~ComTimeout((WUComTimeout::ComTimeout *)&pv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800236c4  mov     r11, rsp
0x1800236c7  mov     [r11+10h], rbx
0x1800236cb  mov     [r11+18h], rdi
0x1800236cf  push    r14
0x1800236d1  sub     rsp, 70h
0x1800236d5  mov     rax, cs:__security_cookie
0x1800236dc  xor     rax, rsp
0x1800236df  mov     [rsp+78h+var_18], rax
0x1800236e4  mov     rdi, rcx
0x1800236e7  lea     r14, aMRemotedeploym; "m_remoteDeploymentSession->SetAttribute"...
0x1800236ee  mov     [r11-48h], r14
0x1800236f2  lea     rax, aComtimeoutMake; "ComTimeout::MakeComCall [%hs]"
0x1800236f9  mov     [r11-50h], rax
0x1800236fd  mov     qword ptr [r11-58h], 0
0x180023705  xor     edx, edx
0x180023707  xor     ecx, ecx
0x180023709  lea     r9d, [rdx+5]
0x18002370d  mov     r8d, 10000h
0x180023713  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180023718  xorps   xmm0, xmm0
0x18002371b  movups  [rsp+78h+pv], xmm0
0x180023720  mov     qword ptr [rsp+78h+pv], 0
0x180023729  mov     word ptr [rsp+78h+pv+0Ch], 0
0x180023730  lea     rcx, [rsp+78h+pv]; pv
0x180023735  call    ?SetTimer@ComTimeout@WUComTimeout@@QEAAJK@Z; WUComTimeout::ComTimeout::SetTimer(ulong)
0x18002373a  mov     ebx, eax
0x18002373c  test    eax, eax
0x18002373e  jns     short loc_18002375E
0x180023740  mov     rcx, [rsp+78h]; this
0x180023745  mov     r9d, eax; char *
0x180023748  lea     r8, aCW1SSrcClientI; "C:\\__w\\1\\s\\src\\Client\\inc\\ComTim"...
0x18002374f  mov     edx, 2Eh ; '.'; void *
0x180023754  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023759  jmp     loc_180023829
0x18002375e  mov     rax, [rdi]
0x180023761  mov     rcx, [rax+88h]
0x180023768  mov     r9, [rdi+10h]
0x18002376c  mov     r8, [rdi+8]
0x180023770  mov     rax, [rcx]
0x180023773  mov     r9, [r9]
0x180023776  mov     r8, [r8]
0x180023779  xor     edx, edx
0x18002377b  mov     rax, [rax+28h]
0x18002377f  call    _guard_dispatch_icall
0x180023784  mov     ebx, eax
0x180023786  test    eax, eax
0x180023788  jns     loc_180023829
0x18002378e  cmp     byte ptr [rsp+78h+pv+0Dh], 0
0x180023793  jz      loc_180023829
0x180023799  lea     rax, aComCallTimedOu; "COM call timed out"
0x1800237a0  mov     [rsp+78h+var_40], rax
0x1800237a5  lea     rax, aFalse; "false"
0x1800237ac  mov     [rsp+78h+var_48], rax
0x1800237b1  lea     rax, aTelemetryasser; "TelemetryAssert (%ws): %ws"
0x1800237b8  mov     [rsp+78h+var_50], rax
0x1800237bd  mov     [rsp+78h+var_58], 0
0x1800237c6  mov     edx, 34h ; '4'
0x1800237cb  lea     r9d, [rdx-31h]
0x1800237cf  lea     r8d, [rdx-14h]
0x1800237d3  lea     rcx, aWucomtimeoutCo; "WUComTimeout::ComTimeout::MakeComCall"
0x1800237da  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800237df  call    ?WUTelemetryAssertTriggered@@YAXII@Z; WUTelemetryAssertTriggered(uint,uint)
0x1800237e4  mov     [rsp+78h+var_30], 1Eh
0x1800237ec  mov     [rsp+78h+var_38], 73Fh
0x1800237f4  lea     rax, aCosdownloaderS; "COSDownloader::SetUpdatePriorityAttribu"...
0x1800237fb  mov     [rsp+78h+var_40], rax
0x180023800  mov     [rsp+78h+var_48], r14
0x180023805  lea     rax, aComCallHsFromH; "COM call [%hs, from %hs:%u] timed out a"...
0x18002380c  mov     [rsp+78h+var_50], rax
0x180023811  mov     dword ptr [rsp+78h+var_58], ebx
0x180023815  xor     edx, edx
0x180023817  xor     ecx, ecx
0x180023819  lea     r9d, [rdx+1]
0x18002381d  mov     r8d, 10000h
0x180023823  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180023828  nop
0x180023829  lea     rcx, [rsp+78h+pv]; this
0x18002382e  call    ??1ComTimeout@WUComTimeout@@QEAA@XZ; WUComTimeout::ComTimeout::~ComTimeout(void)
0x180023833  mov     eax, ebx
0x180023835  mov     rcx, [rsp+78h+var_18]
0x18002383a  xor     rcx, rsp; StackCookie
0x18002383d  call    __security_check_cookie
0x180023842  lea     r11, [rsp+78h+var_8]
0x180023847  mov     rbx, [r11+18h]
0x18002384b  mov     rdi, [r11+20h]
0x18002384f  mov     rsp, r11
0x180023852  pop     r14
0x180023854  retn
```
