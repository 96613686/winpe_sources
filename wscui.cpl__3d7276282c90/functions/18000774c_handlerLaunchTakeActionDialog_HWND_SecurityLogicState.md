# handlerLaunchTakeActionDialog(HWND__ *,SecurityLogicState *)

- ea: `0x18000774c`
- end: `0x18000784d`
- name: `?handlerLaunchTakeActionDialog@@YA_NPEAUHWND__@@PEAVSecurityLogicState@@@Z`
- size: `257`
- prototype: `bool __fastcall(HWND, struct SecurityLogicState *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006520`

## callees

- `0x180005cf4`
- `0x18000774c`
- `0x1800098c4`
- `0x18000a616`
- `0x18000a640`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800077a1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800077a1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800077ac`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800077ac`

## pseudocode

```c
bool __fastcall handlerLaunchTakeActionDialog(HWND a1, struct SecurityLogicState *a2)
{
  const WCHAR *v4; // rcx
  BOOL v5; // ebx
  const struct SecurityActionData *v6; // r8
  int v7; // eax
  unsigned int v8; // r9d
  WCHAR Dst[264]; // [rsp+50h] [rbp-228h] BYREF

  memset_0(Dst, 0, 0x208u);
  v4 = (const WCHAR *)*((_QWORD *)a2 + 9);
  if ( *((_DWORD *)v4 - 4) )
  {
    ExpandEnvironmentStringsW(v4, Dst, 0x104u);
    v5 = PathFileExistsW(Dst);
  }
  else
  {
    v5 = 0;
  }
  if ( (unsigned int)IsIndividualAntiSpywareEnabled() && v5 )
  {
    v6 = (const struct SecurityActionData *)&unk_18000FC40;
LABEL_11:
    v8 = 2;
    return (unsigned int)SecurityLogicControl::ShowRecDlg(
                           a1,
                           a2,
                           v6,
                           v8,
                           (const unsigned __int16 *)0x9F6,
                           (const unsigned __int16 *)0x9F7) == 1;
  }
  v7 = IsIndividualAntiSpywareEnabled();
  if ( v5 )
  {
    v6 = (const struct SecurityActionData *)&unk_18000FC60;
    v8 = 3;
    return (unsigned int)SecurityLogicControl::ShowRecDlg(
                           a1,
                           a2,
                           v6,
                           v8,
                           (const unsigned __int16 *)0x9F6,
                           (const unsigned __int16 *)0x9F7) == 1;
  }
  if ( !v7 )
  {
    v6 = (const struct SecurityActionData *)&unk_18000FC50;
    goto LABEL_11;
  }
  v6 = (const struct SecurityActionData *)&unk_18000FC30;
  v8 = 1;
  return (unsigned int)SecurityLogicControl::ShowRecDlg(
                         a1,
                         a2,
                         v6,
                         v8,
                         (const unsigned __int16 *)0x9F6,
                         (const unsigned __int16 *)0x9F7) == 1;
}

```

## disassembly

```asm
0x18000774c  mov     [rsp+arg_10], rbx
0x180007751  mov     [rsp+arg_18], rsi
0x180007756  push    rdi
0x180007757  sub     rsp, 270h
0x18000775e  mov     rax, cs:__security_cookie
0x180007765  xor     rax, rsp
0x180007768  mov     [rsp+278h+var_18], rax
0x180007770  mov     rdi, rdx
0x180007773  mov     rsi, rcx
0x180007776  xor     edx, edx; Val
0x180007778  lea     rcx, [rsp+278h+Dst]; void *
0x18000777d  mov     r8d, 208h; Size
0x180007783  call    memset_0
0x180007788  mov     rcx, [rdi+48h]; lpSrc
0x18000778c  cmp     dword ptr [rcx-10h], 0
0x180007790  jnz     short loc_180007796
0x180007792  xor     ebx, ebx
0x180007794  jmp     short loc_1800077B9
0x180007796  mov     r8d, 104h; nSize
0x18000779c  lea     rdx, [rsp+278h+Dst]; lpDst
0x1800077a1  call    cs:__imp_ExpandEnvironmentStringsW
0x1800077a7  lea     rcx, [rsp+278h+Dst]; pszPath
0x1800077ac  call    cs:__imp_PathFileExistsW
0x1800077b2  neg     eax
0x1800077b4  sbb     ebx, ebx
0x1800077b6  and     ebx, 1
0x1800077b9  call    ?IsIndividualAntiSpywareEnabled@@YAHXZ; IsIndividualAntiSpywareEnabled(void)
0x1800077be  test    eax, eax
0x1800077c0  jz      short loc_1800077CF
0x1800077c2  test    ebx, ebx
0x1800077c4  jz      short loc_1800077CF
0x1800077c6  lea     r8, unk_18000FC40
0x1800077cd  jmp     short loc_1800077F0
0x1800077cf  call    ?IsIndividualAntiSpywareEnabled@@YAHXZ; IsIndividualAntiSpywareEnabled(void)
0x1800077d4  test    ebx, ebx
0x1800077d6  jnz     short loc_1800077F8
0x1800077d8  test    eax, eax
0x1800077da  jz      short loc_1800077E9
0x1800077dc  lea     r8, unk_18000FC30
0x1800077e3  lea     r9d, [rbx+1]
0x1800077e7  jmp     short loc_180007805
0x1800077e9  lea     r8, unk_18000FC50
0x1800077f0  mov     r9d, 2
0x1800077f6  jmp     short loc_180007805
0x1800077f8  lea     r8, unk_18000FC60; struct SecurityActionData *
0x1800077ff  mov     r9d, 3; unsigned int
0x180007805  mov     [rsp+278h+var_250], 9F7h; unsigned __int16 *
0x18000780e  mov     rdx, rdi; struct SecurityLogicState *
0x180007811  mov     rcx, rsi; HWND
0x180007814  mov     [rsp+278h+var_258], 9F6h; unsigned __int16 *
0x18000781d  call    ?ShowRecDlg@SecurityLogicControl@@SAHPEAUHWND__@@PEAVSecurityLogicState@@PEBUSecurityActionData@@KPEBG3H3PEAH@Z; SecurityLogicControl::ShowRecDlg(HWND__ *,SecurityLogicState *,SecurityActionData const *,ulong,ushort const *,ushort const *,int,ushort const *,int *)
0x180007822  cmp     eax, 1
0x180007825  setz    al
0x180007828  mov     rcx, [rsp+278h+var_18]
0x180007830  xor     rcx, rsp; StackCookie
0x180007833  call    __security_check_cookie
0x180007838  lea     r11, [rsp+278h+var_8]
0x180007840  mov     rbx, [r11+20h]
0x180007844  mov     rsi, [r11+28h]
0x180007848  mov     rsp, r11
0x18000784b  pop     rdi
0x18000784c  retn
```
