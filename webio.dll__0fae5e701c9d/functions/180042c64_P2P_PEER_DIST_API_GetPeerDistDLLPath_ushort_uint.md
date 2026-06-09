# P2P_PEER_DIST_API::GetPeerDistDLLPath(ushort *,uint)

- ea: `0x180042c64`
- end: `0x180042d42`
- name: `?GetPeerDistDLLPath@P2P_PEER_DIST_API@@AEAAKPEAGI@Z`
- size: `222`
- prototype: `unsigned int(P2P_PEER_DIST_API *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180042968`

## callees

- `0x180042c64`
- `0x180043a38`
- `0x1800722f0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180042cae`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180042cae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042cc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042cc0`

## pseudocode

```c
DWORD __fastcall P2P_PEER_DIST_API::GetPeerDistDLLPath(P2P_PEER_DIST_API *this, unsigned __int16 *a2)
{
  DWORD result; // eax
  UINT SystemDirectoryW; // eax
  __int64 v5; // rdx
  unsigned int v6; // r9d
  __int64 i; // r8
  unsigned __int16 v8; // ax
  unsigned int v9[4]; // [rsp+20h] [rbp-238h] BYREF
  unsigned __int16 v10[264]; // [rsp+30h] [rbp-228h] BYREF

  v9[0] = 260;
  *a2 = 0;
  result = GetPeerDistDLLPathFromRegistry((unsigned __int16 *)this, a2, v10, v9);
  if ( !result )
  {
    SystemDirectoryW = GetSystemDirectoryW(a2, 0x104u);
    v5 = SystemDirectoryW;
    if ( SystemDirectoryW )
    {
      if ( SystemDirectoryW > 0x104 )
        return 122;
      v6 = v9[0];
      if ( SystemDirectoryW + v9[0] + 2 > 0x104 )
      {
        return 122;
      }
      else
      {
        if ( a2[SystemDirectoryW - 1] != 92 )
        {
          a2[SystemDirectoryW] = 92;
          v5 = SystemDirectoryW + 1;
        }
        for ( i = 0; (unsigned int)i < v6; v5 = (unsigned int)(v5 + 1) )
        {
          v8 = v10[i];
          i = (unsigned int)(i + 1);
          a2[v5] = v8;
        }
        result = 0;
        a2[v5] = 0;
      }
    }
    else
    {
      return GetLastError();
    }
  }
  return result;
}

```

## disassembly

```asm
0x180042c64  push    rbx
0x180042c66  sub     rsp, 250h
0x180042c6d  mov     rax, cs:__security_cookie
0x180042c74  xor     rax, rsp
0x180042c77  mov     [rsp+258h+var_18], rax
0x180042c7f  xor     eax, eax
0x180042c81  mov     [rsp+258h+var_238], 104h
0x180042c89  lea     r9, [rsp+258h+var_238]; unsigned int *
0x180042c8e  mov     [rdx], ax
0x180042c91  lea     r8, [rsp+258h+var_228]; unsigned __int16 *
0x180042c96  mov     rbx, rdx
0x180042c99  call    ?GetPeerDistDLLPathFromRegistry@@YAKPEBG0PEAGPEAK@Z; GetPeerDistDLLPathFromRegistry(ushort const *,ushort const *,ushort *,ulong *)
0x180042c9e  test    eax, eax
0x180042ca0  jnz     loc_180042D28
0x180042ca6  mov     edx, 104h; uSize
0x180042cab  mov     rcx, rbx; lpBuffer
0x180042cae  call    cs:__imp_GetSystemDirectoryW
0x180042cb5  nop     dword ptr [rax+rax+00h]
0x180042cba  mov     edx, eax
0x180042cbc  test    eax, eax
0x180042cbe  jnz     short loc_180042CCE
0x180042cc0  call    cs:__imp_GetLastError
0x180042cc7  nop     dword ptr [rax+rax+00h]
0x180042ccc  jmp     short loc_180042D28
0x180042cce  cmp     edx, 104h
0x180042cd4  ja      short loc_180042D23
0x180042cd6  mov     r9d, [rsp+258h+var_238]
0x180042cdb  lea     eax, [r9+2]
0x180042cdf  add     eax, edx
0x180042ce1  cmp     eax, 104h
0x180042ce6  ja      short loc_180042D23
0x180042ce8  lea     eax, [rdx-1]
0x180042ceb  mov     r8d, 5Ch ; '\'
0x180042cf1  cmp     [rbx+rax*2], r8w
0x180042cf6  jz      short loc_180042CFF
0x180042cf8  mov     [rbx+rdx*2], r8w
0x180042cfd  inc     edx
0x180042cff  xor     r8d, r8d
0x180042d02  test    r9d, r9d
0x180042d05  jz      short loc_180042D1B
0x180042d07  movzx   eax, [rsp+r8*2+258h+var_228]
0x180042d0d  inc     r8d
0x180042d10  mov     [rbx+rdx*2], ax
0x180042d14  inc     edx
0x180042d16  cmp     r8d, r9d
0x180042d19  jb      short loc_180042D07
0x180042d1b  xor     eax, eax
0x180042d1d  mov     [rbx+rdx*2], ax
0x180042d21  jmp     short loc_180042D28
0x180042d23  mov     eax, 7Ah ; 'z'
0x180042d28  mov     rcx, [rsp+258h+var_18]
0x180042d30  xor     rcx, rsp; StackCookie
0x180042d33  call    __security_check_cookie
0x180042d38  add     rsp, 250h
0x180042d3f  pop     rbx
0x180042d40  retn
```
