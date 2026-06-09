# WinStationQuerySessionVirtualIP

- ea: `0x18002fd70`
- end: `0x18002fef9`
- name: `WinStationQuerySessionVirtualIP`
- size: `393`
- prototype: `__int64 __fastcall(void *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180005b40`
- `0x18000a784`
- `0x1800211d0`
- `0x1800241b0`
- `0x18002fd70`
- `0x180032be6`
- `0x180032c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fe62`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fe62`
- `RPCRT4!RpcBindingFree` at `0x18002fed0`
- `RPCRT4!RpcBindingFree` at `0x18002fed0`

## string_xrefs

- `0x18002fe09`: `bind.Open failed: 0x%x in %s`

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
0x18002fd70  push    rbp
0x18002fd72  push    rbx
0x18002fd73  push    rsi
0x18002fd74  push    rdi
0x18002fd75  push    r14
0x18002fd77  lea     rbp, [rsp-37h]
0x18002fd7c  sub     rsp, 90h
0x18002fd83  mov     rax, cs:__security_cookie
0x18002fd8a  xor     rax, rsp
0x18002fd8d  mov     [rbp+57h+var_30], rax
0x18002fd91  mov     esi, edx
0x18002fd93  movzx   r14d, r8w
0x18002fd97  xor     edx, edx; Val
0x18002fd99  mov     rbx, rcx
0x18002fd9c  lea     rcx, [rbp+57h+var_80]; void *
0x18002fda0  mov     rdi, r9
0x18002fda3  lea     r8d, [rdx+50h]; Size
0x18002fda7  call    memset_0
0x18002fdac  mov     [rbp+57h+Binding], 0
0x18002fdb4  lea     rax, ??_7CTSVIPPublicBinding@@6B@; const CTSVIPPublicBinding::`vftable'
0x18002fdbb  mov     [rbp+57h+var_90], rax
0x18002fdbf  cmp     esi, 0FFFFFFFFh
0x18002fdc2  jnz     short loc_18002FDED
0x18002fdc4  mov     rcx, rbx; void *
0x18002fdc7  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x18002fdcc  test    eax, eax
0x18002fdce  jnz     short loc_18002FDDE
0x18002fdd0  mov     ebx, 80070057h
0x18002fdd5  lea     rdx, aOgonidCurrentS; "OGONID_CURRENT specified for a remote s"...
0x18002fddc  jmp     short loc_18002FE4B
0x18002fdde  mov     rax, gs:60h
0x18002fde7  mov     esi, [rax+2C0h]
0x18002fded  test    rbx, rbx
0x18002fdf0  jnz     short loc_18002FDF6
0x18002fdf2  xor     edx, edx
0x18002fdf4  jmp     short loc_18002FDFA
0x18002fdf6  mov     rdx, [rbx+28h]; unsigned __int16 *
0x18002fdfa  lea     rcx, [rbp+57h+var_90]; this
0x18002fdfe  call    ?Open@CTSVIPPublicBinding@@UEAAJPEBG@Z; CTSVIPPublicBinding::Open(ushort const *)
0x18002fe03  mov     ebx, eax
0x18002fe05  test    eax, eax
0x18002fe07  jns     short loc_18002FE12
0x18002fe09  lea     rdx, aBindOpenFailed; "bind.Open failed: 0x%x in %s"
0x18002fe10  jmp     short loc_18002FE4B
0x18002fe12  lea     r9, [rbp+57h+var_80]; struct __TSVIPSession *
0x18002fe16  mov     r8d, esi; unsigned int
0x18002fe19  movzx   edx, r14w; unsigned __int16
0x18002fe1d  lea     rcx, [rbp+57h+var_90]; this
0x18002fe21  call    ?GetSessionIP@CTSVIPPublicBinding@@QEAAJGKPEAU__TSVIPSession@@@Z; CTSVIPPublicBinding::GetSessionIP(ushort,ulong,__TSVIPSession *)
0x18002fe26  mov     ebx, eax
0x18002fe28  test    eax, eax
0x18002fe2a  jns     short loc_18002FE35
0x18002fe2c  lea     rdx, aBindGetsession; "bind.GetSessionIP failed: 0x%x in %s"
0x18002fe33  jmp     short loc_18002FE4B
0x18002fe35  movzx   eax, [rbp+57h+var_74]
0x18002fe39  cmp     r14w, ax
0x18002fe3d  jz      short loc_18002FE70
0x18002fe3f  mov     ebx, 8007054Fh
0x18002fe44  lea     rdx, aFamilyVipsessi; "Family != VIPSession.SessionIP.IPAddres"...
0x18002fe4b  lea     r9, aWinstationquer_12; "WinStationQuerySessionVirtualIP"
0x18002fe52  mov     r8d, ebx
0x18002fe55  mov     ecx, 8; int
0x18002fe5a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002fe5f  movzx   ecx, bx; dwErrCode
0x18002fe62  call    cs:__imp_SetLastError
0x18002fe69  nop     dword ptr [rax+rax+00h]
0x18002fe6e  jmp     short loc_18002FEB4
0x18002fe70  mov     [rdi], ax
0x18002fe73  cmp     ax, 2
0x18002fe77  jz      short loc_18002FE9E
0x18002fe79  cmp     ax, 17h
0x18002fe7d  jnz     short loc_18002FEB4
0x18002fe7f  movzx   eax, [rbp+57h+var_70]
0x18002fe83  movups  xmm0, [rbp+57h+var_68]
0x18002fe87  mov     [rdi+4], ax
0x18002fe8b  mov     eax, [rbp+57h+var_6C]
0x18002fe8e  mov     [rdi+8], eax
0x18002fe91  mov     eax, [rbp+57h+var_58]
0x18002fe94  mov     [rdi+1Ch], eax
0x18002fe97  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x18002fe9c  jmp     short loc_18002FEB4
0x18002fe9e  movzx   eax, [rbp+57h+var_70]
0x18002fea2  mov     [rdi+4], ax
0x18002fea6  mov     eax, [rbp+57h+var_6C]
0x18002fea9  mov     [rdi+8], eax
0x18002feac  mov     rax, qword ptr [rbp+57h+var_68]
0x18002feb0  mov     [rdi+0Ch], rax
0x18002feb4  shr     ebx, 1Fh
0x18002feb7  lea     rax, ??_7CTSVIPBinding@@6B@; const CTSVIPBinding::`vftable'
0x18002febe  xor     bl, 1
0x18002fec1  mov     [rbp+57h+var_90], rax
0x18002fec5  cmp     [rbp+57h+Binding], 0
0x18002feca  jz      short loc_18002FEDC
0x18002fecc  lea     rcx, [rbp+57h+Binding]; Binding
0x18002fed0  call    cs:__imp_RpcBindingFree
0x18002fed7  nop     dword ptr [rax+rax+00h]
0x18002fedc  mov     al, bl
0x18002fede  mov     rcx, [rbp+57h+var_30]
0x18002fee2  xor     rcx, rsp; StackCookie
0x18002fee5  call    __security_check_cookie
0x18002feea  add     rsp, 90h
0x18002fef1  pop     r14
0x18002fef3  pop     rdi
0x18002fef4  pop     rsi
0x18002fef5  pop     rbx
0x18002fef6  pop     rbp
0x18002fef7  retn
```
