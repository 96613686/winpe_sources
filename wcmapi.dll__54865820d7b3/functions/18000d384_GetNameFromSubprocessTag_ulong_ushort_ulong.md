# GetNameFromSubprocessTag(ulong,ushort *,ulong)

- ea: `0x18000d384`
- end: `0x18000d48f`
- name: `?GetNameFromSubprocessTag@@YAKKPEAGK@Z`
- size: `267`
- prototype: `unsigned int(unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x18000d264`

## callees

- `0x180005280`
- `0x180008a90`
- `0x18000d384`
- `0x180010254`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d3e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d3e1`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000d3ce`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000d3ce`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x18000d403`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x18000d403`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d464`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d464`

## pseudocode

```c
__int64 __fastcall GetNameFromSubprocessTag(unsigned int a1, unsigned __int16 *a2)
{
  wchar_t *v3; // rcx
  DWORD CurrentProcessId; // eax
  unsigned int v6; // ebx
  __int128 v8; // [rsp+20h] [rbp-30h] BYREF
  STRSAFE_PCNZWCH psz; // [rsp+30h] [rbp-20h]
  unsigned int Pid; // [rsp+38h] [rbp-18h] BYREF

  v3 = 0;
  psz = 0;
  v8 = 0;
  if ( a2 && a1 )
  {
    Pid = 0;
    if ( I_RpcBindingInqLocalClientPID(0, &Pid) == 1725 )
      CurrentProcessId = GetCurrentProcessId();
    else
      CurrentProcessId = Pid;
    *(_QWORD *)&v8 = __PAIR64__(a1, CurrentProcessId);
    v6 = I_QueryTagInformation(0, 1, &v8);
    if ( v6 )
    {
LABEL_11:
      v3 = (wchar_t *)psz;
      goto LABEL_14;
    }
    if ( !psz )
      return v6;
    if ( StringLengthWorkerW(psz, 0x103u, 0) >= 0 )
    {
      if ( (int)StringCchCopyW(a2, 0x104u, psz) < 0 )
        v6 = 122;
      goto LABEL_11;
    }
    v3 = (wchar_t *)psz;
    v6 = 122;
  }
  else
  {
    v6 = 87;
  }
LABEL_14:
  if ( v3 )
    LocalFree(v3);
  return v6;
}

```

## disassembly

```asm
0x18000d384  mov     [rsp-8+arg_10], rbx
0x18000d389  mov     [rsp-8+arg_18], rdi
0x18000d38e  push    rbp
0x18000d38f  mov     rbp, rsp
0x18000d392  sub     rsp, 50h
0x18000d396  mov     rax, cs:__security_cookie
0x18000d39d  xor     rax, rsp
0x18000d3a0  mov     [rbp+var_10], rax
0x18000d3a4  mov     ebx, ecx
0x18000d3a6  xorps   xmm0, xmm0
0x18000d3a9  xor     ecx, ecx; hMem
0x18000d3ab  mov     rdi, rdx
0x18000d3ae  mov     [rbp+psz], rcx
0x18000d3b2  movups  [rbp+var_30], xmm0
0x18000d3b6  test    rdx, rdx
0x18000d3b9  jz      loc_18000D45A
0x18000d3bf  test    ebx, ebx
0x18000d3c1  jz      loc_18000D45A
0x18000d3c7  lea     rdx, [rbp+Pid]; Pid
0x18000d3cb  mov     [rbp+Pid], ecx
0x18000d3ce  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000d3d5  nop     dword ptr [rax+rax+00h]
0x18000d3da  cmp     eax, 6BDh
0x18000d3df  jnz     short loc_18000D3EF
0x18000d3e1  call    cs:__imp_GetCurrentProcessId
0x18000d3e8  nop     dword ptr [rax+rax+00h]
0x18000d3ed  jmp     short loc_18000D3F2
0x18000d3ef  mov     eax, [rbp+Pid]
0x18000d3f2  lea     r8, [rbp+var_30]
0x18000d3f6  mov     dword ptr [rbp+var_30], eax
0x18000d3f9  mov     edx, 1
0x18000d3fe  mov     dword ptr [rbp+var_30+4], ebx
0x18000d401  xor     ecx, ecx
0x18000d403  call    cs:__imp_I_QueryTagInformation
0x18000d40a  nop     dword ptr [rax+rax+00h]
0x18000d40f  mov     ebx, eax
0x18000d411  test    eax, eax
0x18000d413  jnz     short loc_18000D449
0x18000d415  mov     rcx, [rbp+psz]; psz
0x18000d419  test    rcx, rcx
0x18000d41c  jz      short loc_18000D470
0x18000d41e  xor     r8d, r8d; pcchLength
0x18000d421  mov     edx, 103h; cchMax
0x18000d426  call    StringLengthWorkerW
0x18000d42b  test    eax, eax
0x18000d42d  js      short loc_18000D44F
0x18000d42f  mov     r8, [rbp+psz]; unsigned __int16 *
0x18000d433  mov     edx, 104h; unsigned __int64
0x18000d438  mov     rcx, rdi; unsigned __int16 *
0x18000d43b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d440  test    eax, eax
0x18000d442  jns     short loc_18000D449
0x18000d444  mov     ebx, 7Ah ; 'z'
0x18000d449  mov     rcx, [rbp+psz]
0x18000d44d  jmp     short loc_18000D45F
0x18000d44f  mov     rcx, [rbp+psz]
0x18000d453  mov     ebx, 7Ah ; 'z'
0x18000d458  jmp     short loc_18000D45F
0x18000d45a  mov     ebx, 57h ; 'W'
0x18000d45f  test    rcx, rcx
0x18000d462  jz      short loc_18000D470
0x18000d464  call    cs:__imp_LocalFree
0x18000d46b  nop     dword ptr [rax+rax+00h]
0x18000d470  mov     eax, ebx
0x18000d472  mov     rcx, [rbp+var_10]
0x18000d476  xor     rcx, rsp; StackCookie
0x18000d479  call    __security_check_cookie
0x18000d47e  mov     rbx, [rsp+50h+arg_10]
0x18000d483  mov     rdi, [rsp+50h+arg_18]
0x18000d488  add     rsp, 50h
0x18000d48c  pop     rbp
0x18000d48d  retn
```
