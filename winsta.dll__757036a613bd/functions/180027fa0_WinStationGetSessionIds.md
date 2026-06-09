# WinStationGetSessionIds

- ea: `0x180027fa0`
- end: `0x180028113`
- name: `WinStationGetSessionIds`
- size: `371`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180027fa0`
- `0x18002fe06`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800280db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800280db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800280eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800280eb`
- `RPCRT4!NdrClientCall3` at `0x18002804b`
- `RPCRT4!NdrClientCall3` at `0x18002804b`

## string_xrefs

- `0x18002806e`: `RpcRevertFromServicesSession threw an exception: 0x%x`

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
    v15.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800320B0, 8u, 0, v7, v12, v13, &hMem, a3).Pointer;
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
0x180027fa0  mov     rax, rsp
0x180027fa3  mov     [rax+8], rbx
0x180027fa7  mov     [rax+18h], r8
0x180027fab  mov     [rax+10h], rdx
0x180027faf  push    rsi
0x180027fb0  push    rdi
0x180027fb1  push    r14
0x180027fb3  sub     rsp, 70h
0x180027fb7  mov     rdi, r8
0x180027fba  mov     r14, rdx
0x180027fbd  mov     ebx, ecx
0x180027fbf  mov     qword ptr [rax-40h], 0
0x180027fc7  xor     r8d, r8d; int
0x180027fca  xor     edx, edx; void *
0x180027fcc  lea     rcx, [rax-30h]; this
0x180027fd0  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180027fd5  test    r14, r14
0x180027fd8  jz      loc_1800280D4
0x180027fde  test    rdi, rdi
0x180027fe1  jz      loc_1800280D4
0x180027fe7  mov     esi, [rdi]
0x180027fe9  mov     [rsp+88h+arg_18], esi
0x180027ff0  test    esi, esi
0x180027ff2  jz      loc_1800280D4
0x180027ff8  mov     dword ptr [rdi], 0
0x180027ffe  mov     r8d, esi
0x180028001  shl     r8, 2; Size
0x180028005  xor     edx, edx; Val
0x180028007  mov     rcx, r14; void *
0x18002800a  call    memset_0
0x18002800f  nop
0x180028010  lea     rcx, [rsp+88h+var_30]; unsigned __int16 *
0x180028015  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002801a  mov     [rsp+88h+var_38], 0
0x180028023  mov     [rsp+88h+var_50], rdi
0x180028028  lea     rcx, [rsp+88h+hMem]
0x18002802d  mov     [rsp+88h+var_58], rcx
0x180028032  mov     [rsp+88h+var_60], esi
0x180028036  mov     [rsp+88h+var_68], ebx
0x18002803a  mov     r9, rax
0x18002803d  xor     r8d, r8d; pReturnValue
0x180028040  lea     edx, [r8+8]; nProcNum
0x180028044  lea     rcx, stru_1800320B0; pProxyInfo
0x18002804b  call    cs:__imp_NdrClientCall3
0x180028051  mov     [rsp+88h+var_38], rax
0x180028056  mov     ecx, eax; int
0x180028058  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18002805d  mov     ebx, eax
0x18002805f  mov     [rsp+88h+var_48], eax
0x180028063  jmp     short loc_180028096
0x180028065  mov     ebx, eax
0x180028067  mov     [rsp+88h+var_48], eax
0x18002806b  mov     r8d, eax
0x18002806e  lea     rdx, aRpcrevertfroms; "RpcRevertFromServicesSession threw an e"...
0x180028075  mov     ecx, 8; int
0x18002807a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002807f  mov     rdi, [rsp+88h+arg_10]
0x180028087  mov     r14, [rsp+88h+arg_8]
0x18002808f  mov     esi, [rsp+88h+arg_18]
0x180028096  test    ebx, ebx
0x180028098  jz      short loc_1800280A2
0x18002809a  cmp     ebx, 0EAh
0x1800280a0  jnz     short loc_1800280D9
0x1800280a2  cmp     dword ptr [rdi], 0
0x1800280a5  jbe     short loc_1800280D9
0x1800280a7  mov     r8, [rsp+88h+hMem]
0x1800280ac  test    r8, r8
0x1800280af  jz      short loc_1800280C7
0x1800280b1  cmp     [rdi], esi
0x1800280b3  ja      short loc_1800280C7
0x1800280b5  xor     edx, edx
0x1800280b7  mov     eax, [r8+rdx*4]
0x1800280bb  mov     [r14+rdx*4], eax
0x1800280bf  inc     edx
0x1800280c1  cmp     edx, [rdi]
0x1800280c3  jb      short loc_1800280B7
0x1800280c5  jmp     short loc_1800280D9
0x1800280c7  mov     ebx, 0Dh
0x1800280cc  mov     dword ptr [rdi], 0
0x1800280d2  jmp     short loc_1800280D9
0x1800280d4  mov     ebx, 57h ; 'W'
0x1800280d9  mov     ecx, ebx; dwErrCode
0x1800280db  call    cs:__imp_SetLastError
0x1800280e1  mov     rcx, [rsp+88h+hMem]; hMem
0x1800280e6  test    rcx, rcx
0x1800280e9  jz      short loc_1800280F1
0x1800280eb  call    cs:__imp_LocalFree
0x1800280f1  test    ebx, ebx
0x1800280f3  setz    bl
0x1800280f6  lea     rcx, [rsp+88h+var_30]; this
0x1800280fb  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180028100  mov     al, bl
0x180028102  mov     rbx, [rsp+88h+arg_0]
0x18002810a  add     rsp, 70h
0x18002810e  pop     r14
0x180028110  pop     rdi
0x180028111  pop     rsi
0x180028112  retn
0x180030873  push    rbp
0x180030875  sub     rsp, 40h
0x180030879  mov     rbp, rdx
0x18003087c  mov     rcx, [rcx]
0x18003087f  mov     ecx, [rcx]; ExceptionCode
0x180030881  call    cs:__imp_I_RpcExceptionFilter
0x180030887  nop
0x180030888  add     rsp, 40h
0x18003088c  pop     rbp
0x18003088d  retn
```
