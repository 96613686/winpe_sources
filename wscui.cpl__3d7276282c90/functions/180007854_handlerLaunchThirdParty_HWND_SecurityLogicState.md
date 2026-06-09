# handlerLaunchThirdParty(HWND__ *,SecurityLogicState *)

- ea: `0x180007854`
- end: `0x180007932`
- name: `?handlerLaunchThirdParty@@YA_NPEAUHWND__@@PEAVSecurityLogicState@@@Z`
- size: `222`
- prototype: `bool __fastcall(HWND, struct SecurityLogicState *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006520`

## callees

- `0x18000750c`
- `0x180007854`
- `0x180007938`
- `0x180008d98`
- `0x18000917c`
- `0x18000a616`
- `0x18000a640`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800078a3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800078a3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800078b8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800078b8`

## pseudocode

```c
char __fastcall handlerLaunchThirdParty(HWND a1, struct SecurityLogicState *a2)
{
  const WCHAR *v4; // rcx
  __int64 v5; // r8
  void *v7; // [rsp+20h] [rbp-238h] BYREF
  WCHAR Dst[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(Dst, 0, 0x208u);
  v4 = (const WCHAR *)*((_QWORD *)a2 + 9);
  v7 = 0;
  if ( !ExpandEnvironmentStringsW(v4, Dst, 0x104u) )
  {
    v5 = 2;
LABEL_12:
    ShowThirdPartyExeError(a1, a2, v5);
    return 0;
  }
  if ( !PathFileExistsW(Dst) )
  {
    v5 = 1;
    goto LABEL_12;
  }
  if ( (int)CheckTrust(Dst, &v7) < 0 )
  {
    if ( v7 )
      FreeWVTStateData(v7);
    v5 = 0;
    goto LABEL_12;
  }
  if ( v7 )
    FreeWVTStateData(v7);
  return handlerLaunchThirdPartyDirect(a1, (LPCWSTR *)a2);
}

```

## disassembly

```asm
0x180007854  mov     [rsp+arg_10], rbx
0x180007859  push    rdi
0x18000785a  sub     rsp, 250h
0x180007861  mov     rax, cs:__security_cookie
0x180007868  xor     rax, rsp
0x18000786b  mov     [rsp+258h+var_18], rax
0x180007873  mov     rbx, rdx
0x180007876  mov     rdi, rcx
0x180007879  xor     edx, edx; Val
0x18000787b  lea     rcx, [rsp+258h+Dst]; void *
0x180007880  mov     r8d, 208h; Size
0x180007886  call    memset_0
0x18000788b  mov     rcx, [rbx+48h]; lpSrc
0x18000788f  lea     rdx, [rsp+258h+Dst]; lpDst
0x180007894  mov     r8d, 104h; nSize
0x18000789a  mov     [rsp+258h+var_238], 0
0x1800078a3  call    cs:__imp_ExpandEnvironmentStringsW
0x1800078a9  test    eax, eax
0x1800078ab  jnz     short loc_1800078B3
0x1800078ad  lea     r8d, [rax+2]
0x1800078b1  jmp     short loc_180007904
0x1800078b3  lea     rcx, [rsp+258h+Dst]; pszPath
0x1800078b8  call    cs:__imp_PathFileExistsW
0x1800078be  test    eax, eax
0x1800078c0  jnz     short loc_1800078C8
0x1800078c2  lea     r8d, [rax+1]
0x1800078c6  jmp     short loc_180007904
0x1800078c8  lea     rdx, [rsp+258h+var_238]; void **
0x1800078cd  lea     rcx, [rsp+258h+Dst]; unsigned __int16 *
0x1800078d2  call    ?CheckTrust@@YAJPEBGAEAPEAX@Z; CheckTrust(ushort const *,void * &)
0x1800078d7  mov     rcx, [rsp+258h+var_238]; void *
0x1800078dc  test    eax, eax
0x1800078de  js      short loc_1800078F7
0x1800078e0  test    rcx, rcx
0x1800078e3  jz      short loc_1800078EA
0x1800078e5  call    ?FreeWVTStateData@@YAJPEAX@Z; FreeWVTStateData(void *)
0x1800078ea  mov     rdx, rbx; struct SecurityLogicState *
0x1800078ed  mov     rcx, rdi; HWND
0x1800078f0  call    ?handlerLaunchThirdPartyDirect@@YA_NPEAUHWND__@@PEAVSecurityLogicState@@@Z; handlerLaunchThirdPartyDirect(HWND__ *,SecurityLogicState *)
0x1800078f5  jmp     short loc_180007911
0x1800078f7  test    rcx, rcx
0x1800078fa  jz      short loc_180007901
0x1800078fc  call    ?FreeWVTStateData@@YAJPEAX@Z; FreeWVTStateData(void *)
0x180007901  xor     r8d, r8d
0x180007904  mov     rdx, rbx
0x180007907  mov     rcx, rdi
0x18000790a  call    ?ShowThirdPartyExeError@@YA_NPEAUHWND__@@PEAVSecurityLogicState@@W4ThirdPartyExeError@@@Z; ShowThirdPartyExeError(HWND__ *,SecurityLogicState *,ThirdPartyExeError)
0x18000790f  xor     al, al
0x180007911  mov     rcx, [rsp+258h+var_18]
0x180007919  xor     rcx, rsp; StackCookie
0x18000791c  call    __security_check_cookie
0x180007921  mov     rbx, [rsp+258h+arg_10]
0x180007929  add     rsp, 250h
0x180007930  pop     rdi
0x180007931  retn
```
