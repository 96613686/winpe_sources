# DispatchUdwmDiagnosticsControlMessage(UdwmDiagnosticsControlMessage const *)

- ea: `0x1800b7c20`
- end: `0x1800b7cd2`
- name: `?DispatchUdwmDiagnosticsControlMessage@@YAXPEBUUdwmDiagnosticsControlMessage@@@Z`
- size: `178`
- prototype: `void __fastcall(const struct UdwmDiagnosticsControlMessage *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18008fa98`

## callees

- `0x180099440`
- `0x1800b7c20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800b7c46`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800b7c46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b7c39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b7c39`

## pseudocode

```c
void __fastcall DispatchUdwmDiagnosticsControlMessage(const struct UdwmDiagnosticsControlMessage *a1)
{
  DWORD CurrentProcessId; // eax
  const char *v3; // r9
  int v4; // r9d
  unsigned int i; // r8d
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  DWORD pSessionId; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_DWORD *)a1 + 6) == -1 )
    goto LABEL_15;
  pSessionId = 0;
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x6B,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\etw.cpp",
      v3);
  if ( pSessionId == *((_DWORD *)a1 + 6) )
  {
LABEL_15:
    if ( !*((_BYTE *)a1 + 2) && !*(_WORD *)a1 && *((_DWORD *)a1 + 4) >= 0x24u )
    {
      v4 = *((_DWORD *)a1 + 7);
      if ( *((unsigned int *)a1 + 4) >= (unsigned __int64)(4LL * (v4 - 1) + 36) )
      {
        for ( i = 0; (int)i < v4; ++i )
        {
          if ( (*((_DWORD *)a1 + i + 8) & 0x7FFFFFFF) == 1 )
            g_simulateDeviceLost = *((_DWORD *)a1 + i + 8) >= 0;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800b7c20  mov     [rsp+arg_8], rbx
0x1800b7c25  push    rdi
0x1800b7c26  sub     rsp, 20h
0x1800b7c2a  xor     edi, edi
0x1800b7c2c  mov     rbx, rcx
0x1800b7c2f  cmp     dword ptr [rcx+18h], 0FFFFFFFFh
0x1800b7c33  jz      short loc_1800B7C6E
0x1800b7c35  mov     [rsp+28h+pSessionId], edi
0x1800b7c39  call    cs:__imp_GetCurrentProcessId
0x1800b7c3f  mov     ecx, eax; dwProcessId
0x1800b7c41  lea     rdx, [rsp+28h+pSessionId]; pSessionId
0x1800b7c46  call    cs:__imp_ProcessIdToSessionId
0x1800b7c4c  test    eax, eax
0x1800b7c4e  jnz     short loc_1800B7C65
0x1800b7c50  mov     rcx, [rsp+28h]; this
0x1800b7c55  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\udwm\\etw.cpp"
0x1800b7c5c  lea     edx, [rdi+6Bh]; void *
0x1800b7c5f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800b7c65  mov     eax, [rbx+18h]
0x1800b7c68  cmp     [rsp+28h+pSessionId], eax
0x1800b7c6c  jnz     short loc_1800B7CC7
0x1800b7c6e  cmp     [rbx+2], dil
0x1800b7c72  jnz     short loc_1800B7CC7
0x1800b7c74  cmp     [rbx], di
0x1800b7c77  jnz     short loc_1800B7CC7
0x1800b7c79  cmp     dword ptr [rbx+10h], 24h ; '$'
0x1800b7c7d  jb      short loc_1800B7CC7
0x1800b7c7f  mov     r9d, [rbx+1Ch]
0x1800b7c83  lea     eax, [r9-1]
0x1800b7c87  movsxd  rcx, eax
0x1800b7c8a  mov     eax, [rbx+10h]
0x1800b7c8d  lea     rcx, ds:24h[rcx*4]
0x1800b7c95  cmp     rax, rcx
0x1800b7c98  jb      short loc_1800B7CC7
0x1800b7c9a  mov     r8d, edi
0x1800b7c9d  test    r9d, r9d
0x1800b7ca0  jle     short loc_1800B7CC7
0x1800b7ca2  mov     eax, r8d
0x1800b7ca5  mov     edx, [rbx+rax*4+20h]
0x1800b7ca9  mov     ecx, edx
0x1800b7cab  btr     ecx, 1Fh
0x1800b7caf  cmp     ecx, 1
0x1800b7cb2  jnz     short loc_1800B7CBF
0x1800b7cb4  shr     edx, 1Fh
0x1800b7cb7  xor     dl, cl
0x1800b7cb9  mov     cs:?g_simulateDeviceLost@@3_NA, dl; bool g_simulateDeviceLost
0x1800b7cbf  inc     r8d
0x1800b7cc2  cmp     r8d, r9d
0x1800b7cc5  jl      short loc_1800B7CA2
0x1800b7cc7  mov     rbx, [rsp+28h+arg_8]
0x1800b7ccc  add     rsp, 20h
0x1800b7cd0  pop     rdi
0x1800b7cd1  retn
```
