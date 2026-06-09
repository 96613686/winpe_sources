# SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)

- ea: `0x1800280f8`
- end: `0x180028274`
- name: `?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z`
- size: `380`
- prototype: `__int64 __fastcall(OLECHAR *psz, LPVOID *)`
- caller_count: `34`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002d20`
- `0x18000312c`
- `0x1800034c4`
- `0x180004518`
- `0x180004d58`
- `0x18000cf00`
- `0x18001483c`
- `0x180014f7c`
- `0x1800151fc`
- `0x180015e30`
- `0x180016080`
- `0x18001790c`
- `0x180017c90`
- `0x1800181a4`
- `0x180018a9c`
- `0x1800192ac`
- `0x18001955c`
- `0x1800199c4`
- `0x180019b88`
- `0x18001b9c8`
- `0x18001c224`
- `0x18001cc2c`
- `0x18001d544`
- `0x18001db84`
- `0x18001e194`
- `0x18001ee38`
- `0x180021914`
- `0x180022350`
- `0x180022570`
- `0x1800227d0`
- `0x180022a30`
- `0x180023b00`
- `0x180023e40`
- `0x180026500`

## callees

- `0x180026fa0`
- `0x1800280f8`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180028176`
- `ole32!CoCreateInstance` at `0x180028176`
- `OLEAUT32!__imp_SysAllocString` at `0x1800281b7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800281b7`
- `OLEAUT32!__imp_SysFreeString` at `0x180028259`
- `OLEAUT32!__imp_SysFreeString` at `0x180028259`

## string_xrefs

- `0x180028135`: `SdpXmlCreate`

## pseudocode

```c
__int64 __fastcall SdpXmlCreate(OLECHAR *psz, LPVOID *a2)
{
  OLECHAR *v4; // rdi
  unsigned int v5; // r8d
  int v6; // r9d
  unsigned int v7; // ebx
  HRESULT v8; // eax
  int v9; // eax
  BSTR v10; // rax
  int v11; // eax
  LPVOID v12; // rcx
  __int16 v14; // [rsp+50h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+18h] BYREF

  v14 = -1;
  ppv = 0;
  v4 = 0;
  if ( !psz )
  {
    v5 = 462;
LABEL_3:
    v6 = -2147024809;
    v7 = -2147024809;
LABEL_4:
    SdpDebugTrace(1u, L"SdpXmlCreate", v5, v6);
    goto LABEL_18;
  }
  if ( !a2 )
  {
    v5 = 463;
    goto LABEL_3;
  }
  v8 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x15u, &IID_IXMLDOMDocument2, &ppv);
  v7 = v8;
  if ( v8 < 0 )
  {
    v6 = v8;
    v5 = 470;
    goto LABEL_4;
  }
  v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  v7 = v9;
  if ( v9 < 0 )
  {
    v6 = v9;
    v5 = 473;
    goto LABEL_4;
  }
  v10 = SysAllocString(psz);
  v4 = v10;
  if ( !v10 )
  {
    v7 = -2147024882;
    v5 = 476;
    v6 = -2147024882;
    goto LABEL_4;
  }
  v11 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int16 *))(*(_QWORD *)ppv + 520LL))(ppv, v10, &v14);
  v7 = v11;
  if ( v11 < 0 )
  {
    v6 = v11;
    v5 = 479;
    goto LABEL_4;
  }
  if ( !v14 )
  {
    v7 = -2147467259;
    v5 = 480;
    v6 = -2147467259;
    goto LABEL_4;
  }
  v12 = ppv;
  *a2 = ppv;
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 8LL))(v12);
LABEL_18:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v4 )
    SysFreeString(v4);
  return v7;
}

```

## disassembly

```asm
0x1800280f8  mov     [rsp+arg_8], rbx
0x1800280fd  mov     [rsp+arg_18], rbp
0x180028102  push    rsi
0x180028103  push    rdi
0x180028104  push    r14
0x180028106  sub     rsp, 30h
0x18002810a  xor     ebp, ebp
0x18002810c  or      eax, 0FFFFFFFFh
0x18002810f  mov     [rsp+48h+arg_0], ax
0x180028114  mov     r14, rdx
0x180028117  mov     [rsp+48h+arg_10], rbp
0x18002811c  mov     rsi, rcx
0x18002811f  mov     edi, ebp
0x180028121  test    rcx, rcx
0x180028124  jnz     short loc_18002814B
0x180028126  mov     r8d, 1CEh; int
0x18002812c  mov     r9d, 80070057h; int
0x180028132  mov     ebx, r9d
0x180028135  lea     rdx, aSdpxmlcreate; "SdpXmlCreate"
0x18002813c  mov     ecx, 1; Level
0x180028141  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180028146  jmp     loc_180028236
0x18002814b  test    r14, r14
0x18002814e  jnz     short loc_180028158
0x180028150  mov     r8d, 1CFh
0x180028156  jmp     short loc_18002812C
0x180028158  xor     edx, edx; pUnkOuter
0x18002815a  lea     rax, [rsp+48h+arg_10]
0x18002815f  lea     r9, IID_IXMLDOMDocument2; riid
0x180028166  mov     [rsp+48h+ppv], rax; ppv
0x18002816b  lea     rcx, CLSID_DOMDocument60; rclsid
0x180028172  lea     r8d, [rdx+15h]; dwClsContext
0x180028176  call    cs:__imp_CoCreateInstance
0x18002817c  mov     ebx, eax
0x18002817e  test    eax, eax
0x180028180  jns     short loc_18002818D
0x180028182  mov     r9d, eax
0x180028185  mov     r8d, 1D6h
0x18002818b  jmp     short loc_180028135
0x18002818d  mov     rcx, [rsp+48h+arg_10]
0x180028192  xor     edx, edx
0x180028194  mov     rax, [rcx]
0x180028197  mov     rax, [rax+1F8h]
0x18002819e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281a3  mov     ebx, eax
0x1800281a5  test    eax, eax
0x1800281a7  jns     short loc_1800281B4
0x1800281a9  mov     r9d, eax
0x1800281ac  mov     r8d, 1D9h
0x1800281b2  jmp     short loc_180028135
0x1800281b4  mov     rcx, rsi; psz
0x1800281b7  call    cs:__imp_SysAllocString
0x1800281bd  mov     rdi, rax
0x1800281c0  test    rax, rax
0x1800281c3  jnz     short loc_1800281D8
0x1800281c5  mov     ebx, 8007000Eh
0x1800281ca  mov     r8d, 1DCh
0x1800281d0  mov     r9d, ebx
0x1800281d3  jmp     loc_180028135
0x1800281d8  mov     rcx, [rsp+48h+arg_10]
0x1800281dd  lea     r8, [rsp+48h+arg_0]
0x1800281e2  mov     rdx, rdi
0x1800281e5  mov     rax, [rcx]
0x1800281e8  mov     rax, [rax+208h]
0x1800281ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281f4  mov     ebx, eax
0x1800281f6  test    eax, eax
0x1800281f8  jns     short loc_180028208
0x1800281fa  mov     r9d, eax
0x1800281fd  mov     r8d, 1DFh
0x180028203  jmp     loc_180028135
0x180028208  cmp     [rsp+48h+arg_0], bp
0x18002820d  jnz     short loc_180028222
0x18002820f  mov     ebx, 80004005h
0x180028214  mov     r8d, 1E0h
0x18002821a  mov     r9d, ebx
0x18002821d  jmp     loc_180028135
0x180028222  mov     rcx, [rsp+48h+arg_10]
0x180028227  mov     [r14], rcx
0x18002822a  mov     rax, [rcx]
0x18002822d  mov     rax, [rax+8]
0x180028231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028236  mov     rcx, [rsp+48h+arg_10]
0x18002823b  test    rcx, rcx
0x18002823e  jz      short loc_180028251
0x180028240  mov     rax, [rcx]
0x180028243  mov     rax, [rax+10h]
0x180028247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002824c  mov     [rsp+48h+arg_10], rbp
0x180028251  test    rdi, rdi
0x180028254  jz      short loc_18002825F
0x180028256  mov     rcx, rdi; bstrString
0x180028259  call    cs:__imp_SysFreeString
0x18002825f  mov     rbp, [rsp+48h+arg_18]
0x180028264  mov     eax, ebx
0x180028266  mov     rbx, [rsp+48h+arg_8]
0x18002826b  add     rsp, 30h
0x18002826f  pop     r14
0x180028271  pop     rdi
0x180028272  pop     rsi
0x180028273  retn
```
