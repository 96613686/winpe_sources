# handlerWindowsDefenderAllActions(HWND__ *,SecurityLogicState *,SecurityAction)

- ea: `0x180007b08`
- end: `0x180007bc1`
- name: `?handlerWindowsDefenderAllActions@@YA_NPEAUHWND__@@PEAVSecurityLogicState@@W4SecurityAction@@@Z`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006520`

## callees

- `0x180001b90`
- `0x18000592c`
- `0x180007120`
- `0x180007b08`
- `0x180009988`
- `0x18000a616`
- `0x18000a640`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180007b5c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180007b5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall handlerWindowsDefenderAllActions(HWND a1, __int64 a2, int a3)
{
  int v5; // r9d
  char v6; // bl
  unsigned __int16 *v8; // [rsp+20h] [rbp-238h] BYREF
  WCHAR Dst[264]; // [rsp+30h] [rbp-228h] BYREF

  GetDefenderParameters((char **)&v8, a3);
  memset_0(Dst, 0, 0x208u);
  if ( ExpandEnvironmentStringsW(*(LPCWSTR *)(a2 + 80), Dst, 0x104u) && LaunchProgram(a1, Dst, v8, v5) )
  {
    v6 = 1;
  }
  else
  {
    v6 = 0;
    SecurityLogicControl::ShowFailDlg(a1, 1155);
  }
  ATL::CStringData::Release((ATL::CStringData *)(v8 - 12));
  return v6;
}

```

## disassembly

```asm
0x180007b08  mov     [rsp+arg_10], rbx
0x180007b0d  push    rdi
0x180007b0e  sub     rsp, 250h
0x180007b15  mov     rax, cs:__security_cookie
0x180007b1c  xor     rax, rsp
0x180007b1f  mov     [rsp+258h+var_18], rax
0x180007b27  mov     rbx, rdx
0x180007b2a  mov     rdi, rcx
0x180007b2d  mov     edx, r8d
0x180007b30  lea     rcx, [rsp+258h+var_238]
0x180007b35  call    ?GetDefenderParameters@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@W4SecurityAction@@@Z; GetDefenderParameters(SecurityAction)
0x180007b3a  nop
0x180007b3b  xor     edx, edx; Val
0x180007b3d  mov     r8d, 208h; Size
0x180007b43  lea     rcx, [rsp+258h+Dst]; void *
0x180007b48  call    memset_0
0x180007b4d  mov     r8d, 104h; nSize
0x180007b53  lea     rdx, [rsp+258h+Dst]; lpDst
0x180007b58  mov     rcx, [rbx+50h]; lpSrc
0x180007b5c  call    cs:__imp_ExpandEnvironmentStringsW
0x180007b62  test    eax, eax
0x180007b64  jz      short loc_180007B80
0x180007b66  mov     r8, [rsp+258h+var_238]; unsigned __int16 *
0x180007b6b  lea     rdx, [rsp+258h+Dst]; unsigned __int16 *
0x180007b70  mov     rcx, rdi; HWND
0x180007b73  call    ?LaunchProgram@@YA_NPEAUHWND__@@PEBG1H@Z; LaunchProgram(HWND__ *,ushort const *,ushort const *,int)
0x180007b78  test    al, al
0x180007b7a  jz      short loc_180007B80
0x180007b7c  mov     bl, 1
0x180007b7e  jmp     short loc_180007B90
0x180007b80  xor     bl, bl
0x180007b82  mov     edx, 483h; int
0x180007b87  mov     rcx, rdi; HWND
0x180007b8a  call    ?ShowFailDlg@SecurityLogicControl@@SAHPEAUHWND__@@H@Z; SecurityLogicControl::ShowFailDlg(HWND__ *,int)
0x180007b8f  nop
0x180007b90  mov     rcx, [rsp+258h+var_238]
0x180007b95  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180007b99  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180007b9e  mov     al, bl
0x180007ba0  mov     rcx, [rsp+258h+var_18]
0x180007ba8  xor     rcx, rsp; StackCookie
0x180007bab  call    __security_check_cookie
0x180007bb0  mov     rbx, [rsp+258h+arg_10]
0x180007bb8  add     rsp, 250h
0x180007bbf  pop     rdi
0x180007bc0  retn
```
