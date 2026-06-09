# ScCheckProtocol

- ea: `0x1800144c0`
- end: `0x180014643`
- name: `ScCheckProtocol`
- size: `387`
- prototype: `__int64 __fastcall(PCNZWCH lpString2)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013f34`
- `0x18004aa18`

## callees

- `0x1800144c0`
- `0x18004f91a`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145f8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800145e5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800145e5`
- `RPCRT4!RpcStringFreeW` at `0x1800145c1`
- `RPCRT4!RpcStringFreeW` at `0x18001460b`
- `RPCRT4!RpcStringFreeW` at `0x1800145c1`
- `RPCRT4!RpcStringFreeW` at `0x18001460b`
- `RPCRT4!RpcBindingFree` at `0x180014621`
- `RPCRT4!RpcBindingFree` at `0x180014621`
- `RPCRT4!RpcStringBindingParseW` at `0x1800145b5`
- `RPCRT4!RpcStringBindingParseW` at `0x1800145b5`
- `RPCRT4!RpcBindingServerFromClient` at `0x180014568`
- `RPCRT4!RpcBindingServerFromClient` at `0x180014568`
- `RPCRT4!RpcServerInqCallAttributesA` at `0x180014545`
- `RPCRT4!RpcServerInqCallAttributesA` at `0x180014545`
- `RPCRT4!RpcSsGetContextBinding` at `0x180014515`
- `RPCRT4!RpcSsGetContextBinding` at `0x180014515`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18001458a`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18001458a`

## pseudocode

```c
__int64 __fastcall ScCheckProtocol(PCNZWCH lpString2, __int64 a2, void *a3, _DWORD *a4)
{
  RPC_STATUS ContextBinding; // eax
  DWORD LastError; // ebx
  int v9; // eax
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp-79h] BYREF
  RPC_WSTR Protseq; // [rsp+38h] [rbp-71h] BYREF
  RPC_WSTR StringBinding[2]; // [rsp+40h] [rbp-69h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v15[48]; // [rsp+58h] [rbp-51h] BYREF
  int v16; // [rsp+88h] [rbp-21h]

  StringBinding[0] = 0;
  Protseq = 0;
  Binding = 0;
  *a4 = 0;
  if ( a3 )
  {
    ContextBinding = RpcSsGetContextBinding(a3, &Binding);
    goto LABEL_7;
  }
  if ( lpString2 )
  {
    ContextBinding = RpcBindingServerFromClient(0, &Binding);
LABEL_7:
    LastError = ContextBinding;
    if ( !ContextBinding )
    {
      if ( lpString2 )
      {
        LastError = RpcBindingToStringBindingW(Binding, StringBinding);
        if ( !LastError )
        {
          LastError = RpcStringBindingParseW(StringBinding[0], 0, &Protseq, 0, 0, 0);
          RpcStringFreeW(StringBinding);
          if ( !LastError )
          {
            v9 = CompareStringW(0x7Fu, 1u, Protseq, -1, lpString2, -1);
            if ( v9 == 2 )
            {
              *a4 = 1;
            }
            else if ( !v9 )
            {
              LastError = GetLastError();
            }
          }
        }
      }
      else
      {
        LastError = 87;
      }
    }
    goto LABEL_16;
  }
  memset_0(v15, 0, 0x70u);
  RpcCallAttributes[0] = 3;
  RpcCallAttributes[1] = 64;
  LastError = RpcServerInqCallAttributesA(0, RpcCallAttributes);
  if ( !LastError )
    *a4 = v16 == 0;
LABEL_16:
  if ( Protseq )
    RpcStringFreeW(&Protseq);
  if ( Binding && !a3 )
    RpcBindingFree(&Binding);
  return LastError;
}

```

## disassembly

```asm
0x1800144c0  push    rbp
0x1800144c2  push    rbx
0x1800144c3  push    rsi
0x1800144c4  push    rdi
0x1800144c5  push    r14
0x1800144c7  lea     rbp, [rsp-37h]
0x1800144cc  sub     rsp, 0E0h
0x1800144d3  mov     rax, cs:__security_cookie
0x1800144da  xor     rax, rsp
0x1800144dd  mov     [rbp+57h+var_30], rax
0x1800144e1  mov     [rbp+57h+StringBinding], 0
0x1800144e9  mov     rsi, r9
0x1800144ec  mov     [rbp+57h+Protseq], 0
0x1800144f4  mov     r14, r8
0x1800144f7  mov     [rbp+57h+Binding], 0
0x1800144ff  mov     rdi, rcx
0x180014502  mov     dword ptr [r9], 0
0x180014509  test    r8, r8
0x18001450c  jz      short loc_18001451D
0x18001450e  lea     rdx, [rbp+57h+Binding]; Binding
0x180014512  mov     rcx, r8; ContextHandle
0x180014515  call    cs:__imp_RpcSsGetContextBinding
0x18001451b  jmp     short loc_18001456E
0x18001451d  test    rdi, rdi
0x180014520  jnz     short loc_180014562
0x180014522  xor     edx, edx; Val
0x180014524  lea     r8d, [rdi+70h]; Size
0x180014528  lea     rcx, [rbp+57h+var_A8]; void *
0x18001452c  call    memset_0
0x180014531  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x180014535  mov     [rbp+57h+RpcCallAttributes], 3
0x18001453c  xor     ecx, ecx; ClientBinding
0x18001453e  mov     [rbp+57h+var_AC], 40h ; '@'
0x180014545  call    cs:__imp_RpcServerInqCallAttributesA
0x18001454b  mov     ebx, eax
0x18001454d  test    eax, eax
0x18001454f  jnz     loc_180014600
0x180014555  cmp     [rbp+57h+var_78], eax
0x180014558  setz    al
0x18001455b  mov     [rsi], eax
0x18001455d  jmp     loc_180014600
0x180014562  lea     rdx, [rbp+57h+Binding]; ServerBinding
0x180014566  xor     ecx, ecx; ClientBinding
0x180014568  call    cs:__imp_RpcBindingServerFromClient
0x18001456e  mov     ebx, eax
0x180014570  test    eax, eax
0x180014572  jnz     loc_180014600
0x180014578  test    rdi, rdi
0x18001457b  jnz     short loc_180014582
0x18001457d  lea     ebx, [rdi+57h]
0x180014580  jmp     short loc_180014600
0x180014582  mov     rcx, [rbp+57h+Binding]; Binding
0x180014586  lea     rdx, [rbp+57h+StringBinding]; StringBinding
0x18001458a  call    cs:__imp_RpcBindingToStringBindingW
0x180014590  mov     ebx, eax
0x180014592  test    eax, eax
0x180014594  jnz     short loc_180014600
0x180014596  mov     rcx, [rbp+57h+StringBinding]; StringBinding
0x18001459a  lea     r8, [rbp+57h+Protseq]; Protseq
0x18001459e  mov     [rsp+100h+NetworkOptions], 0; NetworkOptions
0x1800145a7  xor     r9d, r9d; NetworkAddr
0x1800145aa  xor     edx, edx; ObjUuid
0x1800145ac  mov     [rsp+100h+Endpoint], 0; Endpoint
0x1800145b5  call    cs:__imp_RpcStringBindingParseW
0x1800145bb  lea     rcx, [rbp+57h+StringBinding]; String
0x1800145bf  mov     ebx, eax
0x1800145c1  call    cs:__imp_RpcStringFreeW
0x1800145c7  test    ebx, ebx
0x1800145c9  jnz     short loc_180014600
0x1800145cb  mov     r8, [rbp+57h+Protseq]; lpString1
0x1800145cf  lea     ecx, [rbx+7Fh]; Locale
0x1800145d2  or      r9d, 0FFFFFFFFh; cchCount1
0x1800145d6  mov     dword ptr [rsp+100h+NetworkOptions], r9d; cchCount2
0x1800145db  mov     [rsp+100h+Endpoint], rdi; lpString2
0x1800145e0  lea     edi, [rbx+1]
0x1800145e3  mov     edx, edi; dwCmpFlags
0x1800145e5  call    cs:__imp_CompareStringW
0x1800145eb  cmp     eax, 2
0x1800145ee  jnz     short loc_1800145F4
0x1800145f0  mov     [rsi], edi
0x1800145f2  jmp     short loc_180014600
0x1800145f4  test    eax, eax
0x1800145f6  jnz     short loc_180014600
0x1800145f8  call    cs:__imp_GetLastError
0x1800145fe  mov     ebx, eax
0x180014600  cmp     [rbp+57h+Protseq], 0
0x180014605  jz      short loc_180014611
0x180014607  lea     rcx, [rbp+57h+Protseq]; String
0x18001460b  call    cs:__imp_RpcStringFreeW
0x180014611  cmp     [rbp+57h+Binding], 0
0x180014616  jz      short loc_180014627
0x180014618  test    r14, r14
0x18001461b  jnz     short loc_180014627
0x18001461d  lea     rcx, [rbp+57h+Binding]; Binding
0x180014621  call    cs:__imp_RpcBindingFree
0x180014627  mov     eax, ebx
0x180014629  mov     rcx, [rbp+57h+var_30]
0x18001462d  xor     rcx, rsp; StackCookie
0x180014630  call    __security_check_cookie
0x180014635  add     rsp, 0E0h
0x18001463c  pop     r14
0x18001463e  pop     rdi
0x18001463f  pop     rsi
0x180014640  pop     rbx
0x180014641  pop     rbp
0x180014642  retn
```
