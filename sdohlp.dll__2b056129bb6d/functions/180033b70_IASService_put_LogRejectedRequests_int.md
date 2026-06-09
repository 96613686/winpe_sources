# IASService::put_LogRejectedRequests(int)

- ea: `0x180033b70`
- end: `0x180033caf`
- name: `?put_LogRejectedRequests@IASService@@UEAAJH@Z`
- size: `319`
- prototype: `__int64 __fastcall(IASService *__hidden this, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180029ef4`
- `0x18002cd00`
- `0x18002f240`
- `0x1800325c0`
- `0x180033b70`
- `0x180042a80`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180033b89`
- `OLEAUT32!__imp_VariantInit` at `0x180033b89`

## pseudocode

```c
__int64 __fastcall IASService::put_LogRejectedRequests(IASService *this, int a2)
{
  int NTEventLogObject; // ebx
  int v5; // edx
  SHORT v6; // ax
  struct ISdo *v7; // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-48h] BYREF
  struct tagVARIANT v10; // [rsp+50h] [rbp-28h] BYREF

  VariantInit(&pvarg);
  if ( *((_QWORD *)this + 22)
    || (NTEventLogObject = IASService::GetNTEventLogObject((struct ISdo **)this), NTEventLogObject >= 0) )
  {
    pvarg.vt = 11;
    if ( a2 == 1 )
      v6 = -1;
    else
      v6 = 0;
    v7 = (struct ISdo *)*((_QWORD *)this + 22);
    pvarg.iVal = v6;
    v10 = pvarg;
    NTEventLogObject = PutSdoProperty(v7, 0x403u, &v10);
    if ( NTEventLogObject < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("PuttSdoProperty(PROPERTY_EVENTLOG_LOG_MALFORMED) failed with 0x%x");
      v5 = 38;
      goto LABEL_15;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("GetNTEventLogObject failed with 0x%x");
    v5 = 37;
LABEL_15:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids,
      (unsigned int)"NPSSDO",
      NTEventLogObject);
  }
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  return (unsigned int)NTEventLogObject;
}

```

## disassembly

```asm
0x180033b70  mov     [rsp+arg_0], rbx
0x180033b75  mov     [rsp+arg_8], rsi
0x180033b7a  push    rdi
0x180033b7b  sub     rsp, 70h
0x180033b7f  mov     rdi, rcx
0x180033b82  mov     esi, edx
0x180033b84  lea     rcx, [rsp+78h+pvarg]; pvarg
0x180033b89  call    cs:__imp_VariantInit
0x180033b8f  cmp     qword ptr [rdi+0B0h], 0
0x180033b97  jnz     short loc_180033BED
0x180033b99  mov     rcx, rdi; this
0x180033b9c  call    ?GetNTEventLogObject@IASService@@QEAAJXZ; IASService::GetNTEventLogObject(void)
0x180033ba1  mov     ebx, eax
0x180033ba3  test    eax, eax
0x180033ba5  jns     short loc_180033BED
0x180033ba7  mov     rax, cs:WPP_GLOBAL_Control
0x180033bae  lea     rcx, WPP_GLOBAL_Control
0x180033bb5  cmp     rax, rcx
0x180033bb8  jz      loc_180033C91
0x180033bbe  cmp     byte ptr [rax+19h], 2
0x180033bc2  jb      loc_180033C91
0x180033bc8  test    dword ptr [rax+1Ch], 400h
0x180033bcf  jz      loc_180033C91
0x180033bd5  mov     edx, ebx
0x180033bd7  lea     rcx, aGetnteventlogo; "GetNTEventLogObject failed with 0x%x"
0x180033bde  call    WppDbgPrint
0x180033be3  mov     edx, 25h ; '%'
0x180033be8  jmp     loc_180033C6F
0x180033bed  mov     eax, 0Bh
0x180033bf2  mov     word ptr [rsp+78h+pvarg], ax
0x180033bf7  cmp     esi, 1
0x180033bfa  jnz     short loc_180033C01
0x180033bfc  or      eax, 0FFFFFFFFh
0x180033bff  jmp     short loc_180033C03
0x180033c01  xor     eax, eax
0x180033c03  movsd   xmm1, qword ptr [rsp+78h+pvarg+10h]
0x180033c09  lea     r8, [rsp+78h+var_28]; struct tagVARIANT
0x180033c0e  mov     rcx, [rdi+0B0h]; struct ISdo *
0x180033c15  mov     edx, 403h; unsigned int
0x180033c1a  mov     word ptr [rsp+78h+pvarg+8], ax
0x180033c1f  movups  xmm0, xmmword ptr [rsp+78h+pvarg]
0x180033c24  movsd   qword ptr [rsp+78h+var_28+10h], xmm1
0x180033c2a  movaps  xmmword ptr [rsp+78h+var_28], xmm0
0x180033c2f  call    ?PutSdoProperty@@YAJPEAUISdo@@KUtagVARIANT@@@Z; PutSdoProperty(ISdo *,ulong,tagVARIANT)
0x180033c34  mov     ebx, eax
0x180033c36  test    eax, eax
0x180033c38  jns     short loc_180033C91
0x180033c3a  mov     rax, cs:WPP_GLOBAL_Control
0x180033c41  lea     rcx, WPP_GLOBAL_Control
0x180033c48  cmp     rax, rcx
0x180033c4b  jz      short loc_180033C91
0x180033c4d  cmp     byte ptr [rax+19h], 2
0x180033c51  jb      short loc_180033C91
0x180033c53  test    dword ptr [rax+1Ch], 400h
0x180033c5a  jz      short loc_180033C91
0x180033c5c  mov     edx, ebx
0x180033c5e  lea     rcx, aPuttsdopropert_0; "PuttSdoProperty(PROPERTY_EVENTLOG_LOG_M"...
0x180033c65  call    WppDbgPrint
0x180033c6a  mov     edx, 26h ; '&'
0x180033c6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180033c76  lea     r9, aNpssdo; "NPSSDO"
0x180033c7d  lea     r8, WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids
0x180033c84  mov     [rsp+78h+var_58], ebx
0x180033c88  mov     rcx, [rcx+10h]
0x180033c8c  call    WPP_SF_sd
0x180033c91  lea     rcx, [rsp+78h+pvarg]; this
0x180033c96  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180033c9b  lea     r11, [rsp+78h+var_8]
0x180033ca0  mov     eax, ebx
0x180033ca2  mov     rbx, [r11+10h]
0x180033ca6  mov     rsi, [r11+18h]
0x180033caa  mov     rsp, r11
0x180033cad  pop     rdi
0x180033cae  retn
```
