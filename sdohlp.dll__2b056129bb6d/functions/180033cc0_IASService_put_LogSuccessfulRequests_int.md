# IASService::put_LogSuccessfulRequests(int)

- ea: `0x180033cc0`
- end: `0x180033dff`
- name: `?put_LogSuccessfulRequests@IASService@@UEAAJH@Z`
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
- `0x180033cc0`
- `0x180042a80`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180033cd9`
- `OLEAUT32!__imp_VariantInit` at `0x180033cd9`

## pseudocode

```c
__int64 __fastcall IASService::put_LogSuccessfulRequests(IASService *this, int a2)
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
    NTEventLogObject = PutSdoProperty(v7, 0x404u, &v10);
    if ( NTEventLogObject < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("PuttSdoProperty(PROPERTY_EVENTLOG_LOG_DEBUG) failed with 0x%x");
      v5 = 34;
      goto LABEL_15;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("GetNTEventLogObject failed with 0x%x");
    v5 = 33;
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
0x180033cc0  mov     [rsp+arg_0], rbx
0x180033cc5  mov     [rsp+arg_8], rsi
0x180033cca  push    rdi
0x180033ccb  sub     rsp, 70h
0x180033ccf  mov     rdi, rcx
0x180033cd2  mov     esi, edx
0x180033cd4  lea     rcx, [rsp+78h+pvarg]; pvarg
0x180033cd9  call    cs:__imp_VariantInit
0x180033cdf  cmp     qword ptr [rdi+0B0h], 0
0x180033ce7  jnz     short loc_180033D3D
0x180033ce9  mov     rcx, rdi; this
0x180033cec  call    ?GetNTEventLogObject@IASService@@QEAAJXZ; IASService::GetNTEventLogObject(void)
0x180033cf1  mov     ebx, eax
0x180033cf3  test    eax, eax
0x180033cf5  jns     short loc_180033D3D
0x180033cf7  mov     rax, cs:WPP_GLOBAL_Control
0x180033cfe  lea     rcx, WPP_GLOBAL_Control
0x180033d05  cmp     rax, rcx
0x180033d08  jz      loc_180033DE1
0x180033d0e  cmp     byte ptr [rax+19h], 2
0x180033d12  jb      loc_180033DE1
0x180033d18  test    dword ptr [rax+1Ch], 400h
0x180033d1f  jz      loc_180033DE1
0x180033d25  mov     edx, ebx
0x180033d27  lea     rcx, aGetnteventlogo; "GetNTEventLogObject failed with 0x%x"
0x180033d2e  call    WppDbgPrint
0x180033d33  mov     edx, 21h ; '!'
0x180033d38  jmp     loc_180033DBF
0x180033d3d  mov     eax, 0Bh
0x180033d42  mov     word ptr [rsp+78h+pvarg], ax
0x180033d47  cmp     esi, 1
0x180033d4a  jnz     short loc_180033D51
0x180033d4c  or      eax, 0FFFFFFFFh
0x180033d4f  jmp     short loc_180033D53
0x180033d51  xor     eax, eax
0x180033d53  movsd   xmm1, qword ptr [rsp+78h+pvarg+10h]
0x180033d59  lea     r8, [rsp+78h+var_28]; struct tagVARIANT
0x180033d5e  mov     rcx, [rdi+0B0h]; struct ISdo *
0x180033d65  mov     edx, 404h; unsigned int
0x180033d6a  mov     word ptr [rsp+78h+pvarg+8], ax
0x180033d6f  movups  xmm0, xmmword ptr [rsp+78h+pvarg]
0x180033d74  movsd   qword ptr [rsp+78h+var_28+10h], xmm1
0x180033d7a  movaps  xmmword ptr [rsp+78h+var_28], xmm0
0x180033d7f  call    ?PutSdoProperty@@YAJPEAUISdo@@KUtagVARIANT@@@Z; PutSdoProperty(ISdo *,ulong,tagVARIANT)
0x180033d84  mov     ebx, eax
0x180033d86  test    eax, eax
0x180033d88  jns     short loc_180033DE1
0x180033d8a  mov     rax, cs:WPP_GLOBAL_Control
0x180033d91  lea     rcx, WPP_GLOBAL_Control
0x180033d98  cmp     rax, rcx
0x180033d9b  jz      short loc_180033DE1
0x180033d9d  cmp     byte ptr [rax+19h], 2
0x180033da1  jb      short loc_180033DE1
0x180033da3  test    dword ptr [rax+1Ch], 400h
0x180033daa  jz      short loc_180033DE1
0x180033dac  mov     edx, ebx
0x180033dae  lea     rcx, aPuttsdopropert; "PuttSdoProperty(PROPERTY_EVENTLOG_LOG_D"...
0x180033db5  call    WppDbgPrint
0x180033dba  mov     edx, 22h ; '"'
0x180033dbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180033dc6  lea     r9, aNpssdo; "NPSSDO"
0x180033dcd  lea     r8, WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids
0x180033dd4  mov     [rsp+78h+var_58], ebx
0x180033dd8  mov     rcx, [rcx+10h]
0x180033ddc  call    WPP_SF_sd
0x180033de1  lea     rcx, [rsp+78h+pvarg]; this
0x180033de6  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180033deb  lea     r11, [rsp+78h+var_8]
0x180033df0  mov     eax, ebx
0x180033df2  mov     rbx, [r11+10h]
0x180033df6  mov     rsi, [r11+18h]
0x180033dfa  mov     rsp, r11
0x180033dfd  pop     rdi
0x180033dfe  retn
```
