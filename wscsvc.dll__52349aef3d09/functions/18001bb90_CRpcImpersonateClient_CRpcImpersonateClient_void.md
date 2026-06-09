# CRpcImpersonateClient::~CRpcImpersonateClient(void)

- ea: `0x18001bb90`
- end: `0x18001bbd6`
- name: `??1CRpcImpersonateClient@@QEAA@XZ`
- size: `70`
- prototype: `void __fastcall(CRpcImpersonateClient *__hidden this)`
- caller_count: `12`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001b960`
- `0x180031e24`
- `0x180031efc`
- `0x180033750`
- `0x1800337d0`
- `0x180033b90`
- `0x18003532c`
- `0x1800356b4`
- `0x18003d620`
- `0x18003fe50`
- `0x18003fe74`
- `0x1800401b0`

## callees

- `0x180008e48`
- `0x18001bb90`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x18001bb94`
- `RPCRT4!RpcRevertToSelf` at `0x18001bb94`

## pseudocode

```c
void __fastcall CRpcImpersonateClient::~CRpcImpersonateClient(CRpcImpersonateClient *this)
{
  unsigned int v1; // eax

  v1 = RpcRevertToSelf();
  if ( v1
    && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v1);
  }
}

```

## disassembly

```asm
0x18001bb90  sub     rsp, 28h
0x18001bb94  call    cs:__imp_RpcRevertToSelf
0x18001bb9a  test    eax, eax
0x18001bb9c  jnz     short loc_18001BBA3
0x18001bb9e  add     rsp, 28h
0x18001bba2  retn
0x18001bba3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbaa  lea     rdx, WPP_GLOBAL_Control
0x18001bbb1  cmp     rcx, rdx
0x18001bbb4  jz      short loc_18001BB9E
0x18001bbb6  test    byte ptr [rcx+1Ch], 1
0x18001bbba  jz      short loc_18001BB9E
0x18001bbbc  mov     rcx, [rcx+10h]
0x18001bbc0  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x18001bbc7  mov     edx, 1Ch
0x18001bbcc  mov     r9d, eax
0x18001bbcf  call    WPP_SF_d
0x18001bbd4  jmp     short loc_18001BB9E
```
