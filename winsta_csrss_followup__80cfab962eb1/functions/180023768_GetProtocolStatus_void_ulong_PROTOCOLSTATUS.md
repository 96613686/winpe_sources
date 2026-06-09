# GetProtocolStatus(void *,ulong,_PROTOCOLSTATUS *)

- ea: `0x180023768`
- end: `0x1800239b2`
- name: `?GetProtocolStatus@@YAJPEAXKPEAU_PROTOCOLSTATUS@@@Z`
- size: `586`
- prototype: `__int64 __fastcall(void *, unsigned int, struct _PROTOCOLSTATUS *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003480`
- `0x1800049a0`

## callees

- `0x1800041a0`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x180023768`
- `0x180032be6`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002398b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002398b`
- `RPCRT4!NdrClientCall3` at `0x18002382a`
- `RPCRT4!NdrClientCall3` at `0x18002382a`

## string_xrefs

- `0x180023859`: `RpcGetProtocolStatus failed: 0x%x`
- `0x1800238a7`: `RpcGetProtocolStatus returned %d bytes, expected %d`
- `0x1800237d1`: `Invoke RpcGetProtocolStatus`

## pseudocode

```c
__int64 __fastcall GetProtocolStatus(void *a1, int a2, struct _PROTOCOLSTATUS *a3)
{
  signed int LastError; // eax
  CLIENT_CALL_RETURN v6; // rbx
  __int64 v7; // rax
  _OWORD *v8; // rax
  __int64 v9; // rcx
  HLOCAL hMem; // [rsp+48h] [rbp-30h] BYREF
  CLIENT_CALL_RETURN v12; // [rsp+50h] [rbp-28h]
  unsigned __int16 v13[16]; // [rsp+58h] [rbp-20h] BYREF
  unsigned int v14; // [rsp+98h] [rbp+20h] BYREF

  hMem = 0;
  v14 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v13, a1, 1);
  if ( CSmartPublicBinding::operator void *(v13) )
  {
    _DbgPrintMessage(1, "Invoke RpcGetProtocolStatus");
    v7 = CSmartPublicBinding::operator void *(v13);
    v12.Simple = 0;
    v6.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035078, 2u, 0, v7, a2, 0, &hMem, &v14).Pointer;
    v12.Pointer = v6.Pointer;
    if ( SLODWORD(v6.Simple) < 0 )
    {
      if ( LODWORD(v6.Pointer) == -2147022646
        || LODWORD(v6.Pointer) == -2147023174
        || LODWORD(v6.Pointer) == -2147023179 )
      {
        memset_0(a3, 0, 0x3F4u);
        LODWORD(v6.Pointer) = 0;
      }
    }
    else if ( hMem )
    {
      if ( v14 >= 0x3F4 )
      {
        v8 = hMem;
        v9 = 7;
        do
        {
          *(_OWORD *)a3 = *v8;
          *((_OWORD *)a3 + 1) = v8[1];
          *((_OWORD *)a3 + 2) = v8[2];
          *((_OWORD *)a3 + 3) = v8[3];
          *((_OWORD *)a3 + 4) = v8[4];
          *((_OWORD *)a3 + 5) = v8[5];
          *((_OWORD *)a3 + 6) = v8[6];
          *((_OWORD *)a3 + 7) = v8[7];
          a3 = (struct _PROTOCOLSTATUS *)((char *)a3 + 128);
          v8 += 8;
          --v9;
        }
        while ( v9 );
        *(_OWORD *)a3 = *v8;
        *((_OWORD *)a3 + 1) = v8[1];
        *((_OWORD *)a3 + 2) = v8[2];
        *((_OWORD *)a3 + 3) = v8[3];
        *((_OWORD *)a3 + 4) = v8[4];
        *((_OWORD *)a3 + 5) = v8[5];
        *((_OWORD *)a3 + 6) = v8[6];
        *((_DWORD *)a3 + 28) = *((_DWORD *)v8 + 28);
      }
      else
      {
        _DbgPrintMessage(8, "RpcGetProtocolStatus returned %d bytes, expected %d", v14, 1012);
        LODWORD(v6.Pointer) = -2147024809;
      }
    }
    else
    {
      LODWORD(v6.Pointer) = -2147467261;
    }
  }
  else
  {
    LastError = GetLastError();
    LODWORD(v6.Pointer) = LastError;
    if ( LastError > 0 )
      LODWORD(v6.Pointer) = (unsigned __int16)LastError | 0x80070000;
  }
  if ( hMem )
    LocalFree(hMem);
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v13);
  return LODWORD(v6.Pointer);
}

```

## disassembly

```asm
0x180023768  mov     rax, rsp
0x18002376b  mov     [rax+8], rbx
0x18002376f  mov     [rax+18h], r8
0x180023773  push    rdi
0x180023774  sub     rsp, 70h
0x180023778  mov     rdi, r8
0x18002377b  mov     ebx, edx
0x18002377d  mov     qword ptr [rax-30h], 0
0x180023785  mov     dword ptr [rax+20h], 0
0x18002378c  mov     r8d, 1; int
0x180023792  mov     rdx, rcx; void *
0x180023795  lea     rcx, [rax-20h]; this
0x180023799  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18002379e  lea     rcx, [rsp+78h+var_20]; unsigned __int16 *
0x1800237a3  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800237a8  test    rax, rax
0x1800237ab  jnz     short loc_1800237D1
0x1800237ad  call    cs:__imp_GetLastError
0x1800237b4  nop     dword ptr [rax+rax+00h]
0x1800237b9  mov     ebx, eax
0x1800237bb  test    eax, eax
0x1800237bd  jle     loc_180023981
0x1800237c3  movzx   ebx, ax
0x1800237c6  or      ebx, 80070000h
0x1800237cc  jmp     loc_180023981
0x1800237d1  lea     rdx, aInvokeRpcgetpr; "Invoke RpcGetProtocolStatus"
0x1800237d8  mov     ecx, 1; int
0x1800237dd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800237e2  nop
0x1800237e3  lea     rcx, [rsp+78h+var_20]; unsigned __int16 *
0x1800237e8  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800237ed  mov     [rsp+78h+var_28], 0
0x1800237f6  lea     rcx, [rsp+78h+arg_18]
0x1800237fe  mov     [rsp+78h+var_40], rcx
0x180023803  lea     rcx, [rsp+78h+hMem]
0x180023808  mov     [rsp+78h+var_48], rcx
0x18002380d  mov     [rsp+78h+var_50], 0
0x180023815  mov     [rsp+78h+var_58], ebx
0x180023819  mov     r9, rax
0x18002381c  xor     r8d, r8d; pReturnValue
0x18002381f  lea     edx, [r8+2]; nProcNum
0x180023823  lea     rcx, stru_180035078; pProxyInfo
0x18002382a  call    cs:__imp_NdrClientCall3
0x180023831  nop     dword ptr [rax+rax+00h]
0x180023836  mov     rbx, rax
0x180023839  mov     [rsp+78h+var_28], rax
0x18002383e  mov     [rsp+78h+var_38], eax
0x180023842  jmp     short loc_180023872
0x180023844  test    eax, eax
0x180023846  jle     short loc_180023850
0x180023848  movzx   eax, ax
0x18002384b  or      eax, 80070000h
0x180023850  mov     ebx, eax
0x180023852  mov     [rsp+78h+var_38], eax
0x180023856  mov     r8d, eax
0x180023859  lea     rdx, aRpcgetprotocol_0; "RpcGetProtocolStatus failed: 0x%x"
0x180023860  mov     ecx, 8; int
0x180023865  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002386a  mov     rdi, [rsp+78h+arg_10]
0x180023872  test    ebx, ebx
0x180023874  js      loc_180023957
0x18002387a  cmp     [rsp+78h+hMem], 0
0x180023880  jnz     short loc_18002388C
0x180023882  mov     ebx, 80004003h
0x180023887  jmp     loc_180023981
0x18002388c  mov     r8d, 3F4h
0x180023892  cmp     [rsp+78h+arg_18], r8d
0x18002389a  jnb     short loc_1800238C2
0x18002389c  mov     r9d, r8d
0x18002389f  mov     r8d, [rsp+78h+arg_18]
0x1800238a7  lea     rdx, aRpcgetprotocol; "RpcGetProtocolStatus returned %d bytes,"...
0x1800238ae  mov     ecx, 8; int
0x1800238b3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800238b8  mov     ebx, 80070057h
0x1800238bd  jmp     loc_180023981
0x1800238c2  mov     rax, [rsp+78h+hMem]
0x1800238c7  mov     ecx, 7
0x1800238cc  lea     edx, [rcx+79h]
0x1800238cf  movups  xmm0, xmmword ptr [rax]
0x1800238d2  movups  xmmword ptr [rdi], xmm0
0x1800238d5  movups  xmm1, xmmword ptr [rax+10h]
0x1800238d9  movups  xmmword ptr [rdi+10h], xmm1
0x1800238dd  movups  xmm0, xmmword ptr [rax+20h]
0x1800238e1  movups  xmmword ptr [rdi+20h], xmm0
0x1800238e5  movups  xmm1, xmmword ptr [rax+30h]
0x1800238e9  movups  xmmword ptr [rdi+30h], xmm1
0x1800238ed  movups  xmm0, xmmword ptr [rax+40h]
0x1800238f1  movups  xmmword ptr [rdi+40h], xmm0
0x1800238f5  movups  xmm1, xmmword ptr [rax+50h]
0x1800238f9  movups  xmmword ptr [rdi+50h], xmm1
0x1800238fd  movups  xmm0, xmmword ptr [rax+60h]
0x180023901  movups  xmmword ptr [rdi+60h], xmm0
0x180023905  movups  xmm1, xmmword ptr [rax+70h]
0x180023909  movups  xmmword ptr [rdi+70h], xmm1
0x18002390d  add     rdi, rdx
0x180023910  add     rax, rdx
0x180023913  sub     rcx, 1
0x180023917  jnz     short loc_1800238CF
0x180023919  movups  xmm0, xmmword ptr [rax]
0x18002391c  movups  xmmword ptr [rdi], xmm0
0x18002391f  movups  xmm1, xmmword ptr [rax+10h]
0x180023923  movups  xmmword ptr [rdi+10h], xmm1
0x180023927  movups  xmm0, xmmword ptr [rax+20h]
0x18002392b  movups  xmmword ptr [rdi+20h], xmm0
0x18002392f  movups  xmm1, xmmword ptr [rax+30h]
0x180023933  movups  xmmword ptr [rdi+30h], xmm1
0x180023937  movups  xmm0, xmmword ptr [rax+40h]
0x18002393b  movups  xmmword ptr [rdi+40h], xmm0
0x18002393f  movups  xmm1, xmmword ptr [rax+50h]
0x180023943  movups  xmmword ptr [rdi+50h], xmm1
0x180023947  movups  xmm0, xmmword ptr [rax+60h]
0x18002394b  movups  xmmword ptr [rdi+60h], xmm0
0x18002394f  mov     eax, [rax+70h]
0x180023952  mov     [rdi+70h], eax
0x180023955  jmp     short loc_180023981
0x180023957  cmp     ebx, 800708CAh
0x18002395d  jz      short loc_18002396F
0x18002395f  cmp     ebx, 800706BAh
0x180023965  jz      short loc_18002396F
0x180023967  cmp     ebx, 800706B5h
0x18002396d  jnz     short loc_180023981
0x18002396f  xor     edx, edx; Val
0x180023971  mov     r8d, 3F4h; Size
0x180023977  mov     rcx, rdi; void *
0x18002397a  call    memset_0
0x18002397f  xor     ebx, ebx
0x180023981  mov     rcx, [rsp+78h+hMem]; hMem
0x180023986  test    rcx, rcx
0x180023989  jz      short loc_180023997
0x18002398b  call    cs:__imp_LocalFree
0x180023992  nop     dword ptr [rax+rax+00h]
0x180023997  lea     rcx, [rsp+78h+var_20]; this
0x18002399c  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x1800239a1  mov     eax, ebx
0x1800239a3  mov     rbx, [rsp+78h+arg_0]
0x1800239ab  add     rsp, 70h
0x1800239af  pop     rdi
0x1800239b0  retn
0x18003377f  push    rbp
0x180033781  sub     rsp, 40h
0x180033785  mov     rbp, rdx
0x180033788  mov     rcx, [rcx]
0x18003378b  mov     ecx, [rcx]; ExceptionCode
0x18003378d  call    cs:__imp_I_RpcExceptionFilter
0x180033794  nop     dword ptr [rax+rax+00h]
0x180033799  nop
0x18003379a  add     rsp, 40h
0x18003379e  pop     rbp
0x18003379f  retn
```
