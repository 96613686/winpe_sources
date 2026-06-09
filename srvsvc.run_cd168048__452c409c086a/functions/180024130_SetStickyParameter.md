# SetStickyParameter

- ea: `0x180024130`
- end: `0x180024407`
- name: `SetStickyParameter`
- size: `727`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002038`
- `0x180012734`
- `0x1800214a4`
- `0x180024130`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180024162`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002417a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180024192`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800241aa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800241c2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800241da`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800241f2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002420a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180024222`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002423a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180024252`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002426a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180024282`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002429a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800242d0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180024162`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002417a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180024192`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800241aa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800241c2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800241da`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800241f2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002420a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180024222`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002423a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180024252`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002426a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180024282`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002429a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800242d0`

## string_xrefs

- `0x180024230`: `ServiceDllUnloadOnStop`
- `0x180024218`: `ServiceDll`
- `0x180024290`: `Comment`

## pseudocode

```c
__int64 __fastcall SetStickyParameter(const WCHAR *a1, int a2, unsigned __int64 a3, int a4, const WCHAR *a5)
{
  __int64 i; // rax
  __int64 v10; // rdx
  __int64 *v11; // r10
  int v12; // ecx
  int v13; // ecx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v18; // [rsp+20h] [rbp-28h] BYREF
  LPCWSTR Strings[4]; // [rsp+28h] [rbp-20h] BYREF

  v18 = 0;
  *(_OWORD *)Strings = 0;
  if ( !(unsigned int)_o__wcsicmp(a1, L"Size")
    || !(unsigned int)_o__wcsicmp(a1, L"NullSessionShares")
    || !(unsigned int)_o__wcsicmp(a1, L"NullSessionPipes")
    || !(unsigned int)_o__wcsicmp(a1, L"PipesNeedLicense")
    || !(unsigned int)_o__wcsicmp(a1, L"ErrorLogIgnore")
    || !(unsigned int)_o__wcsicmp(a1, L"Guid")
    || !(unsigned int)_o__wcsicmp(a1, L"OptionalNames")
    || !(unsigned int)_o__wcsicmp(a1, L"NoRemapPipes")
    || !(unsigned int)_o__wcsicmp(a1, L"ServiceDll")
    || !(unsigned int)_o__wcsicmp(a1, L"ServiceDllUnloadOnStop")
    || !(unsigned int)_o__wcsicmp(a1, L"EnableS4U2SelfForClaims")
    || !(unsigned int)_o__wcsicmp(a1, L"CAPRequiresS4U2SelfForClaims")
    || !(unsigned int)_o__wcsicmp(a1, L"Disc")
    || !(unsigned int)_o__wcsicmp(a1, L"Comment") )
  {
    return 0;
  }
  v18 = 0;
  for ( i = 0; ; i = ++v18 )
  {
    v10 = SsServerInfoFields[6 * i];
    if ( !v10 )
      return 0;
    if ( !(unsigned int)_o__wcsicmp(a1, v10) )
      break;
  }
  v11 = &SsServerInfoFields[6 * v18];
  if ( !v11 || !*((_DWORD *)v11 + 6) )
    return 0;
  v12 = *((_DWORD *)v11 + 2);
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( v13 )
    {
      if ( v13 != 1 )
      {
LABEL_38:
        SsSetField(v11, &v18, 0, 0);
        return 0;
      }
      if ( a2 != 1 )
      {
        Strings[1] = a5;
        Strings[0] = a1;
        SsLogEvent(0x800009CA, 2u, Strings);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          v15 = 78;
LABEL_35:
          WPP_SF_S(v14[2], v15, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids, a1);
          return 0;
        }
        return 0;
      }
      v16 = a3 & -(__int64)(a4 != 0);
LABEL_37:
      v18 = v16;
      goto LABEL_38;
    }
  }
  if ( a2 == 4 )
  {
    v16 = *(unsigned int *)a3;
    goto LABEL_37;
  }
  Strings[0] = a1;
  Strings[1] = a5;
  SsLogEvent(0x800009CA, 2u, Strings);
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    v15 = 77;
    goto LABEL_35;
  }
  return 0;
}

```

## disassembly

```asm
0x180024130  push    rbp
0x180024132  push    rbx
0x180024133  push    rsi
0x180024134  push    rdi
0x180024135  push    r12
0x180024137  push    r14
0x180024139  mov     rbp, rsp
0x18002413c  sub     rsp, 48h
0x180024140  mov     r14d, edx
0x180024143  mov     [rbp+var_28], 0
0x18002414b  xorps   xmm0, xmm0
0x18002414e  lea     rdx, aSize; "Size"
0x180024155  movups  xmmword ptr [rbp+Strings], xmm0
0x180024159  mov     esi, r9d
0x18002415c  mov     rdi, r8
0x18002415f  mov     rbx, rcx
0x180024162  call    cs:__imp__o__wcsicmp
0x180024168  test    eax, eax
0x18002416a  jz      loc_1800243F8
0x180024170  lea     rdx, aNullsessionsha; "NullSessionShares"
0x180024177  mov     rcx, rbx
0x18002417a  call    cs:__imp__o__wcsicmp
0x180024180  test    eax, eax
0x180024182  jz      loc_1800243F8
0x180024188  lea     rdx, aNullsessionpip; "NullSessionPipes"
0x18002418f  mov     rcx, rbx
0x180024192  call    cs:__imp__o__wcsicmp
0x180024198  test    eax, eax
0x18002419a  jz      loc_1800243F8
0x1800241a0  lea     rdx, aPipesneedlicen; "PipesNeedLicense"
0x1800241a7  mov     rcx, rbx
0x1800241aa  call    cs:__imp__o__wcsicmp
0x1800241b0  test    eax, eax
0x1800241b2  jz      loc_1800243F8
0x1800241b8  lea     rdx, aErrorlogignore; "ErrorLogIgnore"
0x1800241bf  mov     rcx, rbx
0x1800241c2  call    cs:__imp__o__wcsicmp
0x1800241c8  test    eax, eax
0x1800241ca  jz      loc_1800243F8
0x1800241d0  lea     rdx, ValueName; "Guid"
0x1800241d7  mov     rcx, rbx
0x1800241da  call    cs:__imp__o__wcsicmp
0x1800241e0  test    eax, eax
0x1800241e2  jz      loc_1800243F8
0x1800241e8  lea     rdx, aOptionalnames; "OptionalNames"
0x1800241ef  mov     rcx, rbx
0x1800241f2  call    cs:__imp__o__wcsicmp
0x1800241f8  test    eax, eax
0x1800241fa  jz      loc_1800243F8
0x180024200  lea     rdx, aNoremappipes; "NoRemapPipes"
0x180024207  mov     rcx, rbx
0x18002420a  call    cs:__imp__o__wcsicmp
0x180024210  test    eax, eax
0x180024212  jz      loc_1800243F8
0x180024218  lea     rdx, aServicedll; "ServiceDll"
0x18002421f  mov     rcx, rbx
0x180024222  call    cs:__imp__o__wcsicmp
0x180024228  test    eax, eax
0x18002422a  jz      loc_1800243F8
0x180024230  lea     rdx, aServicedllunlo; "ServiceDllUnloadOnStop"
0x180024237  mov     rcx, rbx
0x18002423a  call    cs:__imp__o__wcsicmp
0x180024240  test    eax, eax
0x180024242  jz      loc_1800243F8
0x180024248  lea     rdx, aEnables4u2self; "EnableS4U2SelfForClaims"
0x18002424f  mov     rcx, rbx
0x180024252  call    cs:__imp__o__wcsicmp
0x180024258  test    eax, eax
0x18002425a  jz      loc_1800243F8
0x180024260  lea     rdx, aCaprequiress4u; "CAPRequiresS4U2SelfForClaims"
0x180024267  mov     rcx, rbx
0x18002426a  call    cs:__imp__o__wcsicmp
0x180024270  test    eax, eax
0x180024272  jz      loc_1800243F8
0x180024278  lea     rdx, aDisc_0; "Disc"
0x18002427f  mov     rcx, rbx
0x180024282  call    cs:__imp__o__wcsicmp
0x180024288  test    eax, eax
0x18002428a  jz      loc_1800243F8
0x180024290  lea     rdx, aComment; "Comment"
0x180024297  mov     rcx, rbx
0x18002429a  call    cs:__imp__o__wcsicmp
0x1800242a0  test    eax, eax
0x1800242a2  jz      loc_1800243F8
0x1800242a8  mov     [rbp+var_28], 0
0x1800242b0  lea     r12, SsServerInfoFields
0x1800242b7  xor     eax, eax
0x1800242b9  lea     rax, [rax+rax*2]
0x1800242bd  add     rax, rax
0x1800242c0  mov     rdx, [r12+rax*8]
0x1800242c4  test    rdx, rdx
0x1800242c7  jz      loc_1800243F8
0x1800242cd  mov     rcx, rbx
0x1800242d0  call    cs:__imp__o__wcsicmp
0x1800242d6  test    eax, eax
0x1800242d8  mov     rax, [rbp+var_28]
0x1800242dc  jz      short loc_1800242E7
0x1800242de  inc     rax
0x1800242e1  mov     [rbp+var_28], rax
0x1800242e5  jmp     short loc_1800242B9
0x1800242e7  lea     r10, [rax+rax*2]
0x1800242eb  shl     r10, 4
0x1800242ef  add     r10, r12
0x1800242f2  jz      loc_1800243F8
0x1800242f8  cmp     dword ptr [r10+18h], 0
0x1800242fd  jz      loc_1800243F8
0x180024303  mov     ecx, [r10+8]
0x180024307  test    ecx, ecx
0x180024309  jz      short loc_18002437D
0x18002430b  sub     ecx, 1
0x18002430e  jz      short loc_18002437D
0x180024310  cmp     ecx, 1
0x180024313  jnz     loc_1800243E6
0x180024319  cmp     r14d, ecx
0x18002431c  jz      short loc_180024373
0x18002431e  mov     rax, [rbp+arg_20]
0x180024322  lea     edx, [rcx+1]; wNumStrings
0x180024325  mov     ecx, 800009CAh; dwEventID
0x18002432a  mov     [rbp+Strings+8], rax
0x18002432e  xor     r9d, r9d
0x180024331  mov     [rbp+Strings], rbx
0x180024335  lea     r8, [rbp+Strings]; lpStrings
0x180024339  call    SsLogEvent
0x18002433e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024345  lea     rax, WPP_GLOBAL_Control
0x18002434c  cmp     rcx, rax
0x18002434f  jz      loc_1800243F8
0x180024355  test    dword ptr [rcx+1Ch], 100h
0x18002435c  jz      loc_1800243F8
0x180024362  cmp     byte ptr [rcx+19h], 1
0x180024366  jb      loc_1800243F8
0x18002436c  mov     edx, 4Eh ; 'N'
0x180024371  jmp     short loc_1800243CB
0x180024373  neg     esi
0x180024375  sbb     rax, rax
0x180024378  and     rax, rdi
0x18002437b  jmp     short loc_1800243E2
0x18002437d  cmp     r14d, 4
0x180024381  jz      short loc_1800243E0
0x180024383  mov     rax, [rbp+arg_20]
0x180024387  lea     r8, [rbp+Strings]; lpStrings
0x18002438b  xor     r9d, r9d
0x18002438e  mov     [rbp+Strings], rbx
0x180024392  mov     ecx, 800009CAh; dwEventID
0x180024397  mov     [rbp+Strings+8], rax
0x18002439b  lea     edx, [r9+2]; wNumStrings
0x18002439f  call    SsLogEvent
0x1800243a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800243ab  lea     rax, WPP_GLOBAL_Control
0x1800243b2  cmp     rcx, rax
0x1800243b5  jz      short loc_1800243F8
0x1800243b7  test    dword ptr [rcx+1Ch], 100h
0x1800243be  jz      short loc_1800243F8
0x1800243c0  cmp     byte ptr [rcx+19h], 1
0x1800243c4  jb      short loc_1800243F8
0x1800243c6  mov     edx, 4Dh ; 'M'
0x1800243cb  mov     rcx, [rcx+10h]
0x1800243cf  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x1800243d6  mov     r9, rbx
0x1800243d9  call    WPP_SF_S
0x1800243de  jmp     short loc_1800243F8
0x1800243e0  mov     eax, [rdi]
0x1800243e2  mov     [rbp+var_28], rax
0x1800243e6  xor     r9d, r9d
0x1800243e9  lea     rdx, [rbp+var_28]
0x1800243ed  xor     r8d, r8d
0x1800243f0  mov     rcx, r10
0x1800243f3  call    SsSetField
0x1800243f8  xor     eax, eax
0x1800243fa  add     rsp, 48h
0x1800243fe  pop     r14
0x180024400  pop     r12
0x180024402  pop     rdi
0x180024403  pop     rsi
0x180024404  pop     rbx
0x180024405  pop     rbp
0x180024406  retn
```
