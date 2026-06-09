# WinStationQuerySessionVirtualIP

- ea: `0x18002d8d0`
- end: `0x18002da4c`
- name: `WinStationQuerySessionVirtualIP`
- size: `380`
- prototype: `__int64 __fastcall(void *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180004554`
- `0x180007890`
- `0x18001fad0`
- `0x180022890`
- `0x18002d8d0`
- `0x18002fe06`
- `0x18002fe40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d9c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d9c2`
- `RPCRT4!RpcBindingFree` at `0x18002da2a`
- `RPCRT4!RpcBindingFree` at `0x18002da2a`

## string_xrefs

- `0x18002d969`: `bind.Open failed: 0x%x in %s`

## pseudocode

```c
bool __fastcall WinStationQuerySessionVirtualIP(WCHAR **a1, ULONG SessionId, unsigned __int16 a3, __int64 a4)
{
  int SessionIP; // ebx
  WCHAR *v9; // rdx
  __int16 v10; // ax
  __int128 v11; // xmm0
  bool v12; // bl
  void **v14; // [rsp+20h] [rbp-39h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+28h] [rbp-31h] BYREF
  _BYTE v16[12]; // [rsp+30h] [rbp-29h] BYREF
  __int16 v17; // [rsp+3Ch] [rbp-1Dh]
  __int16 v18; // [rsp+40h] [rbp-19h]
  int v19; // [rsp+44h] [rbp-15h]
  __int128 v20; // [rsp+48h] [rbp-11h]
  int v21; // [rsp+58h] [rbp-1h]

  memset_0(v16, 0, 0x50u);
  Binding = 0;
  v14 = &CTSVIPPublicBinding::`vftable';
  if ( SessionId == -1 )
  {
    if ( !(unsigned int)IsLocalServer(a1) )
    {
      SessionIP = -2147024809;
      _DbgPrintMessage(
        8,
        "OGONID_CURRENT specified for a remote server! failed: 0x%x in %s",
        2147942487LL,
        "WinStationQuerySessionVirtualIP");
LABEL_14:
      SetLastError((unsigned __int16)SessionIP);
      goto LABEL_19;
    }
    SessionId = NtCurrentPeb()->SessionId;
  }
  if ( a1 )
    v9 = a1[5];
  else
    v9 = 0;
  SessionIP = CTSVIPPublicBinding::Open((CTSVIPPublicBinding *)&v14, v9);
  if ( SessionIP < 0 )
  {
    _DbgPrintMessage(8, "bind.Open failed: 0x%x in %s", (unsigned int)SessionIP, "WinStationQuerySessionVirtualIP");
    goto LABEL_14;
  }
  SessionIP = CTSVIPPublicBinding::GetSessionIP(
                (CTSVIPPublicBinding *)&v14,
                a3,
                SessionId,
                (struct __TSVIPSession *)v16);
  if ( SessionIP < 0 )
  {
    _DbgPrintMessage(
      8,
      "bind.GetSessionIP failed: 0x%x in %s",
      (unsigned int)SessionIP,
      "WinStationQuerySessionVirtualIP");
    goto LABEL_14;
  }
  v10 = v17;
  if ( a3 != v17 )
  {
    SessionIP = -2147023537;
    _DbgPrintMessage(
      8,
      "Family != VIPSession.SessionIP.IPAddress.sin_family failed: 0x%x in %s",
      2147943759LL,
      "WinStationQuerySessionVirtualIP");
    goto LABEL_14;
  }
  *(_WORD *)a4 = v17;
  if ( v10 == 2 )
  {
    *(_WORD *)(a4 + 4) = v18;
    *(_DWORD *)(a4 + 8) = v19;
    *(_QWORD *)(a4 + 12) = v20;
  }
  else if ( v10 == 23 )
  {
    v11 = v20;
    *(_WORD *)(a4 + 4) = v18;
    *(_DWORD *)(a4 + 8) = v19;
    *(_DWORD *)(a4 + 28) = v21;
    *(_OWORD *)(a4 + 12) = v11;
  }
LABEL_19:
  v12 = SessionIP >= 0;
  v14 = &CTSVIPBinding::`vftable';
  if ( Binding )
    RpcBindingFree(&Binding);
  return v12;
}

```

## disassembly

```asm
0x18002d8d0  push    rbp
0x18002d8d2  push    rbx
0x18002d8d3  push    rsi
0x18002d8d4  push    rdi
0x18002d8d5  push    r14
0x18002d8d7  lea     rbp, [rsp-37h]
0x18002d8dc  sub     rsp, 90h
0x18002d8e3  mov     rax, cs:__security_cookie
0x18002d8ea  xor     rax, rsp
0x18002d8ed  mov     [rbp+57h+var_30], rax
0x18002d8f1  mov     esi, edx
0x18002d8f3  movzx   r14d, r8w
0x18002d8f7  xor     edx, edx; Val
0x18002d8f9  mov     rbx, rcx
0x18002d8fc  lea     rcx, [rbp+57h+var_80]; void *
0x18002d900  mov     rdi, r9
0x18002d903  lea     r8d, [rdx+50h]; Size
0x18002d907  call    memset_0
0x18002d90c  mov     [rbp+57h+Binding], 0
0x18002d914  lea     rax, ??_7CTSVIPPublicBinding@@6B@; const CTSVIPPublicBinding::`vftable'
0x18002d91b  mov     [rbp+57h+var_90], rax
0x18002d91f  cmp     esi, 0FFFFFFFFh
0x18002d922  jnz     short loc_18002D94D
0x18002d924  mov     rcx, rbx; void *
0x18002d927  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x18002d92c  test    eax, eax
0x18002d92e  jnz     short loc_18002D93E
0x18002d930  mov     ebx, 80070057h
0x18002d935  lea     rdx, aOgonidCurrentS; "OGONID_CURRENT specified for a remote s"...
0x18002d93c  jmp     short loc_18002D9AB
0x18002d93e  mov     rax, gs:60h
0x18002d947  mov     esi, [rax+2C0h]
0x18002d94d  test    rbx, rbx
0x18002d950  jnz     short loc_18002D956
0x18002d952  xor     edx, edx
0x18002d954  jmp     short loc_18002D95A
0x18002d956  mov     rdx, [rbx+28h]; unsigned __int16 *
0x18002d95a  lea     rcx, [rbp+57h+var_90]; this
0x18002d95e  call    ?Open@CTSVIPPublicBinding@@UEAAJPEBG@Z; CTSVIPPublicBinding::Open(ushort const *)
0x18002d963  mov     ebx, eax
0x18002d965  test    eax, eax
0x18002d967  jns     short loc_18002D972
0x18002d969  lea     rdx, aBindOpenFailed; "bind.Open failed: 0x%x in %s"
0x18002d970  jmp     short loc_18002D9AB
0x18002d972  lea     r9, [rbp+57h+var_80]; struct __TSVIPSession *
0x18002d976  mov     r8d, esi; unsigned int
0x18002d979  movzx   edx, r14w; unsigned __int16
0x18002d97d  lea     rcx, [rbp+57h+var_90]; this
0x18002d981  call    ?GetSessionIP@CTSVIPPublicBinding@@QEAAJGKPEAU__TSVIPSession@@@Z; CTSVIPPublicBinding::GetSessionIP(ushort,ulong,__TSVIPSession *)
0x18002d986  mov     ebx, eax
0x18002d988  test    eax, eax
0x18002d98a  jns     short loc_18002D995
0x18002d98c  lea     rdx, aBindGetsession; "bind.GetSessionIP failed: 0x%x in %s"
0x18002d993  jmp     short loc_18002D9AB
0x18002d995  movzx   eax, [rbp+57h+var_74]
0x18002d999  cmp     r14w, ax
0x18002d99d  jz      short loc_18002D9CA
0x18002d99f  mov     ebx, 8007054Fh
0x18002d9a4  lea     rdx, aFamilyVipsessi; "Family != VIPSession.SessionIP.IPAddres"...
0x18002d9ab  lea     r9, aWinstationquer_12; "WinStationQuerySessionVirtualIP"
0x18002d9b2  mov     r8d, ebx
0x18002d9b5  mov     ecx, 8; int
0x18002d9ba  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d9bf  movzx   ecx, bx; dwErrCode
0x18002d9c2  call    cs:__imp_SetLastError
0x18002d9c8  jmp     short loc_18002DA0E
0x18002d9ca  mov     [rdi], ax
0x18002d9cd  cmp     ax, 2
0x18002d9d1  jz      short loc_18002D9F8
0x18002d9d3  cmp     ax, 17h
0x18002d9d7  jnz     short loc_18002DA0E
0x18002d9d9  movzx   eax, [rbp+57h+var_70]
0x18002d9dd  movups  xmm0, [rbp+57h+var_68]
0x18002d9e1  mov     [rdi+4], ax
0x18002d9e5  mov     eax, [rbp+57h+var_6C]
0x18002d9e8  mov     [rdi+8], eax
0x18002d9eb  mov     eax, [rbp+57h+var_58]
0x18002d9ee  mov     [rdi+1Ch], eax
0x18002d9f1  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x18002d9f6  jmp     short loc_18002DA0E
0x18002d9f8  movzx   eax, [rbp+57h+var_70]
0x18002d9fc  mov     [rdi+4], ax
0x18002da00  mov     eax, [rbp+57h+var_6C]
0x18002da03  mov     [rdi+8], eax
0x18002da06  mov     rax, qword ptr [rbp+57h+var_68]
0x18002da0a  mov     [rdi+0Ch], rax
0x18002da0e  shr     ebx, 1Fh
0x18002da11  lea     rax, ??_7CTSVIPBinding@@6B@; const CTSVIPBinding::`vftable'
0x18002da18  xor     bl, 1
0x18002da1b  mov     [rbp+57h+var_90], rax
0x18002da1f  cmp     [rbp+57h+Binding], 0
0x18002da24  jz      short loc_18002DA30
0x18002da26  lea     rcx, [rbp+57h+Binding]; Binding
0x18002da2a  call    cs:__imp_RpcBindingFree
0x18002da30  mov     al, bl
0x18002da32  mov     rcx, [rbp+57h+var_30]
0x18002da36  xor     rcx, rsp; StackCookie
0x18002da39  call    __security_check_cookie
0x18002da3e  add     rsp, 90h
0x18002da45  pop     r14
0x18002da47  pop     rdi
0x18002da48  pop     rsi
0x18002da49  pop     rbx
0x18002da4a  pop     rbp
0x18002da4b  retn
```
