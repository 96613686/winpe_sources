# WinStationGetSessionIds

- ea: `0x180029ad0`
- end: `0x180029c56`
- name: `WinStationGetSessionIds`
- size: `390`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x180029ad0`
- `0x180032be6`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029c11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029c11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029c27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029c27`
- `RPCRT4!NdrClientCall3` at `0x180029b7b`
- `RPCRT4!NdrClientCall3` at `0x180029b7b`

## string_xrefs

- `0x180029ba4`: `RpcRevertFromServicesSession threw an exception: 0x%x`

## pseudocode

```c
bool __fastcall WinStationGetSessionIds(int a1, void *a2, unsigned int *a3)
{
  unsigned int v6; // esi
  void *v7; // rax
  DWORD v8; // ebx
  _DWORD *v9; // r8
  __int64 v10; // rdx
  int v12; // [rsp+20h] [rbp-68h]
  int v13; // [rsp+28h] [rbp-60h]
  HLOCAL hMem; // [rsp+48h] [rbp-40h] BYREF
  CLIENT_CALL_RETURN v15; // [rsp+50h] [rbp-38h]
  unsigned __int16 v16[24]; // [rsp+58h] [rbp-30h] BYREF

  hMem = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v16, 0, 0);
  if ( a2 && a3 && (v6 = *a3) != 0 )
  {
    *a3 = 0;
    memset_0(a2, 0, 4LL * v6);
    v7 = CSmartPublicBinding::operator void *(v16);
    v15.Simple = 0;
    v13 = v6;
    v12 = a1;
    v15.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035048, 8u, 0, v7, v12, v13, &hMem, a3).Pointer;
    v8 = ConvertHRESULT2WIN32(v15.Simple);
    if ( (!v8 || v8 == 234) && *a3 )
    {
      v9 = hMem;
      if ( hMem && *a3 <= v6 )
      {
        v10 = 0;
        do
        {
          *((_DWORD *)a2 + v10) = v9[v10];
          v10 = (unsigned int)(v10 + 1);
        }
        while ( (unsigned int)v10 < *a3 );
      }
      else
      {
        v8 = 13;
        *a3 = 0;
      }
    }
  }
  else
  {
    v8 = 87;
  }
  SetLastError(v8);
  if ( hMem )
    LocalFree(hMem);
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v16);
  return v8 == 0;
}

```

## disassembly

```asm
0x180029ad0  mov     rax, rsp
0x180029ad3  mov     [rax+8], rbx
0x180029ad7  mov     [rax+18h], r8
0x180029adb  mov     [rax+10h], rdx
0x180029adf  push    rsi
0x180029ae0  push    rdi
0x180029ae1  push    r14
0x180029ae3  sub     rsp, 70h
0x180029ae7  mov     rdi, r8
0x180029aea  mov     r14, rdx
0x180029aed  mov     ebx, ecx
0x180029aef  mov     qword ptr [rax-40h], 0
0x180029af7  xor     r8d, r8d; int
0x180029afa  xor     edx, edx; void *
0x180029afc  lea     rcx, [rax-30h]; this
0x180029b00  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180029b05  test    r14, r14
0x180029b08  jz      loc_180029C0A
0x180029b0e  test    rdi, rdi
0x180029b11  jz      loc_180029C0A
0x180029b17  mov     esi, [rdi]
0x180029b19  mov     [rsp+88h+arg_18], esi
0x180029b20  test    esi, esi
0x180029b22  jz      loc_180029C0A
0x180029b28  mov     dword ptr [rdi], 0
0x180029b2e  mov     r8d, esi
0x180029b31  shl     r8, 2; Size
0x180029b35  xor     edx, edx; Val
0x180029b37  mov     rcx, r14; void *
0x180029b3a  call    memset_0
0x180029b3f  nop
0x180029b40  lea     rcx, [rsp+88h+var_30]; unsigned __int16 *
0x180029b45  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180029b4a  mov     [rsp+88h+var_38], 0
0x180029b53  mov     [rsp+88h+var_50], rdi
0x180029b58  lea     rcx, [rsp+88h+hMem]
0x180029b5d  mov     [rsp+88h+var_58], rcx
0x180029b62  mov     [rsp+88h+var_60], esi
0x180029b66  mov     [rsp+88h+var_68], ebx
0x180029b6a  mov     r9, rax
0x180029b6d  xor     r8d, r8d; pReturnValue
0x180029b70  lea     edx, [r8+8]; nProcNum
0x180029b74  lea     rcx, stru_180035048; pProxyInfo
0x180029b7b  call    cs:__imp_NdrClientCall3
0x180029b82  nop     dword ptr [rax+rax+00h]
0x180029b87  mov     [rsp+88h+var_38], rax
0x180029b8c  mov     ecx, eax; int
0x180029b8e  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180029b93  mov     ebx, eax
0x180029b95  mov     [rsp+88h+var_48], eax
0x180029b99  jmp     short loc_180029BCC
0x180029b9b  mov     ebx, eax
0x180029b9d  mov     [rsp+88h+var_48], eax
0x180029ba1  mov     r8d, eax
0x180029ba4  lea     rdx, aRpcrevertfroms; "RpcRevertFromServicesSession threw an e"...
0x180029bab  mov     ecx, 8; int
0x180029bb0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029bb5  mov     rdi, [rsp+88h+arg_10]
0x180029bbd  mov     r14, [rsp+88h+arg_8]
0x180029bc5  mov     esi, [rsp+88h+arg_18]
0x180029bcc  test    ebx, ebx
0x180029bce  jz      short loc_180029BD8
0x180029bd0  cmp     ebx, 0EAh
0x180029bd6  jnz     short loc_180029C0F
0x180029bd8  cmp     dword ptr [rdi], 0
0x180029bdb  jbe     short loc_180029C0F
0x180029bdd  mov     r8, [rsp+88h+hMem]
0x180029be2  test    r8, r8
0x180029be5  jz      short loc_180029BFD
0x180029be7  cmp     [rdi], esi
0x180029be9  ja      short loc_180029BFD
0x180029beb  xor     edx, edx
0x180029bed  mov     eax, [r8+rdx*4]
0x180029bf1  mov     [r14+rdx*4], eax
0x180029bf5  inc     edx
0x180029bf7  cmp     edx, [rdi]
0x180029bf9  jb      short loc_180029BED
0x180029bfb  jmp     short loc_180029C0F
0x180029bfd  mov     ebx, 0Dh
0x180029c02  mov     dword ptr [rdi], 0
0x180029c08  jmp     short loc_180029C0F
0x180029c0a  mov     ebx, 57h ; 'W'
0x180029c0f  mov     ecx, ebx; dwErrCode
0x180029c11  call    cs:__imp_SetLastError
0x180029c18  nop     dword ptr [rax+rax+00h]
0x180029c1d  mov     rcx, [rsp+88h+hMem]; hMem
0x180029c22  test    rcx, rcx
0x180029c25  jz      short loc_180029C33
0x180029c27  call    cs:__imp_LocalFree
0x180029c2e  nop     dword ptr [rax+rax+00h]
0x180029c33  test    ebx, ebx
0x180029c35  setz    bl
0x180029c38  lea     rcx, [rsp+88h+var_30]; this
0x180029c3d  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180029c42  mov     al, bl
0x180029c44  mov     rbx, [rsp+88h+arg_0]
0x180029c4c  add     rsp, 70h
0x180029c50  pop     r14
0x180029c52  pop     rdi
0x180029c53  pop     rsi
0x180029c54  retn
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
