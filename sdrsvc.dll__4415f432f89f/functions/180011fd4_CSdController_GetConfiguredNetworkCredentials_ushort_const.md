# CSdController::_GetConfiguredNetworkCredentials(ushort const *)

- ea: `0x180011fd4`
- end: `0x1800120d3`
- name: `?_GetConfiguredNetworkCredentials@CSdController@@AEAAJPEBG@Z`
- size: `255`
- prototype: `__int64 __fastcall(CSdController *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180012948`

## callees

- `0x180011fd4`
- `0x18001586c`
- `0x180015974`
- `0x1800171f4`
- `0x1800179f4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012077`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001209f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012077`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001209f`

## string_xrefs

- `0x180011fe9`: `CSdController::_GetConfiguredNetworkCredentials`

## pseudocode

```c
__int64 __fastcall CSdController::_GetConfiguredNetworkCredentials(CSdController *this, const unsigned __int16 *a2)
{
  bool v4; // zf
  struct _SID *v5; // r8
  __int16 v6; // ax
  int ConfiguredNetworkCredentials; // ebx
  char *v8; // rcx
  char *v9; // rcx
  void *v11; // [rsp+20h] [rbp-40h] BYREF
  int v12; // [rsp+28h] [rbp-38h] BYREF
  __int16 v13; // [rsp+2Ch] [rbp-34h]
  __int16 v14; // [rsp+2Eh] [rbp-32h]

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v12,
    "CSdController::_GetConfiguredNetworkCredentials",
    2519,
    0);
  v11 = 0;
  if ( !a2 || !*a2 )
  {
    v6 = 2525;
    goto LABEL_12;
  }
  v12 = 0;
  v13 = 2525;
  v4 = (unsigned int)SdIsPathUNC(a2) == 0;
  v6 = 2526;
  if ( !v4 )
  {
LABEL_12:
    ConfiguredNetworkCredentials = -2147024809;
    v14 = v6;
    v12 = -2147024809;
    goto LABEL_13;
  }
  v12 = 0;
  v13 = 2526;
  ConfiguredNetworkCredentials = GetConfiguredNetworkCredentials(a2, &v11, v5);
  v12 = ConfiguredNetworkCredentials;
  if ( ConfiguredNetworkCredentials >= 0 )
  {
    v9 = (char *)*((_QWORD *)this + 19);
    v13 = 2528;
    if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v9);
      ConfiguredNetworkCredentials = v12;
      *((_QWORD *)this + 19) = 0;
    }
    v8 = 0;
    *((_QWORD *)this + 19) = v11;
  }
  else
  {
    v8 = (char *)v11;
    v14 = 2528;
  }
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
LABEL_13:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12);
  return (unsigned int)ConfiguredNetworkCredentials;
}

```

## disassembly

```asm
0x180011fd4  mov     [rsp-18h+arg_10], rbx
0x180011fd9  push    rbp
0x180011fda  push    rsi
0x180011fdb  push    rdi
0x180011fdc  mov     rbp, rsp
0x180011fdf  sub     rsp, 60h
0x180011fe3  mov     rbx, rdx
0x180011fe6  mov     rdi, rcx
0x180011fe9  lea     rdx, aCsdcontrollerG; "CSdController::_GetConfiguredNetworkCre"...
0x180011ff0  xor     r9d, r9d; unsigned __int16
0x180011ff3  lea     rcx, [rbp+var_38]; this
0x180011ff7  mov     r8d, 9D7h; unsigned __int16
0x180011ffd  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180012002  xor     esi, esi
0x180012004  mov     [rbp+var_40], rsi
0x180012008  test    rbx, rbx
0x18001200b  jz      loc_1800120A7
0x180012011  cmp     [rbx], si
0x180012014  jz      loc_1800120A7
0x18001201a  mov     eax, 9DDh
0x18001201f  mov     [rbp+var_38], esi
0x180012022  mov     rcx, rbx; unsigned __int16 *
0x180012025  mov     [rbp+var_34], ax
0x180012029  call    ?SdIsPathUNC@@YAJPEBG@Z; SdIsPathUNC(ushort const *)
0x18001202e  test    eax, eax
0x180012030  mov     eax, 9DEh
0x180012035  jnz     short loc_1800120AC
0x180012037  lea     rdx, [rbp+var_40]; void **
0x18001203b  mov     [rbp+var_38], esi
0x18001203e  mov     rcx, rbx; unsigned __int16 *
0x180012041  mov     [rbp+var_34], ax
0x180012045  call    ?GetConfiguredNetworkCredentials@@YAJPEBGPEAPEAXPEAU_SID@@@Z; GetConfiguredNetworkCredentials(ushort const *,void * *,_SID *)
0x18001204a  mov     ebx, eax
0x18001204c  mov     [rbp+var_38], eax
0x18001204f  test    eax, eax
0x180012051  mov     eax, 9E0h
0x180012056  jns     short loc_180012062
0x180012058  mov     rcx, [rbp+var_40]
0x18001205c  mov     [rbp+var_32], ax
0x180012060  jmp     short loc_180012095
0x180012062  mov     rcx, [rdi+98h]; hObject
0x180012069  mov     [rbp+var_34], ax
0x18001206d  lea     rax, [rcx-1]
0x180012071  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012075  ja      short loc_180012087
0x180012077  call    cs:__imp_CloseHandle
0x18001207d  mov     ebx, [rbp+var_38]
0x180012080  mov     [rdi+98h], rsi
0x180012087  mov     rax, [rbp+var_40]
0x18001208b  mov     rcx, rsi; hObject
0x18001208e  mov     [rdi+98h], rax
0x180012095  lea     rax, [rcx-1]
0x180012099  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001209d  ja      short loc_1800120B8
0x18001209f  call    cs:__imp_CloseHandle
0x1800120a5  jmp     short loc_1800120B8
0x1800120a7  mov     eax, 9DDh
0x1800120ac  mov     ebx, 80070057h
0x1800120b1  mov     [rbp+var_32], ax
0x1800120b5  mov     [rbp+var_38], ebx
0x1800120b8  lea     rcx, [rbp+var_38]; this
0x1800120bc  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800120c1  mov     eax, ebx
0x1800120c3  mov     rbx, [rsp+60h+arg_10]
0x1800120cb  add     rsp, 60h
0x1800120cf  pop     rdi
0x1800120d0  pop     rsi
0x1800120d1  pop     rbp
0x1800120d2  retn
```
