# GetShutdownInfo

- ea: `0x180010e70`
- end: `0x180010f36`
- name: `GetShutdownInfo`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800113d0`

## callees

- `0x180010e70`

## import_xrefs

- `CSRSRV!CsrUnlockThread` at `0x180010f23`
- `CSRSRV!CsrUnlockThread` at `0x180010f23`
- `CSRSRV!CsrLockThreadByClientId` at `0x180010ebb`
- `CSRSRV!CsrLockThreadByClientId` at `0x180010ebb`
- `USER32!GetWindowThreadProcessId` at `0x180010e9e`
- `USER32!GetWindowThreadProcessId` at `0x180010e9e`

## pseudocode

```c
int __fastcall GetShutdownInfo(HWND a1, _DWORD *a2)
{
  __int64 v3; // rax
  _QWORD *v4; // rdx
  __int64 v5; // r8
  int v6; // r9d
  _QWORD *v7; // rcx
  DWORD dwProcessId; // [rsp+38h] [rbp+10h] BYREF
  _QWORD *v10; // [rsp+40h] [rbp+18h] BYREF

  *a2 = 0;
  a2[1] = -1;
  a2[2] = -1;
  dwProcessId = 0;
  v10 = 0;
  LODWORD(v3) = GetWindowThreadProcessId(a1, &dwProcessId);
  if ( (_DWORD)v3 && (LODWORD(v3) = CsrLockThreadByClientId((int)v3, (int)dwProcessId, &v10), (int)v3 >= 0) )
  {
    v4 = v10;
    LODWORD(v3) = dwProcessId;
    v5 = v10[7];
    if ( *(_QWORD *)v5 == dwProcessId )
    {
      v6 = 0;
      v7 = *(_QWORD **)(v5 + 32);
      while ( v7 != (_QWORD *)(v5 + 32) )
      {
        LODWORD(v3) = (_DWORD)v7 - 8;
        if ( v7 - 1 == v10 )
        {
          *a2 = *(_DWORD *)(v5 + 120);
          v3 = v4[7];
          a2[1] = *(_DWORD *)(v3 + 88);
          a2[2] = v6;
          break;
        }
        v7 = (_QWORD *)*v7;
        ++v6;
      }
    }
  }
  else
  {
    v4 = v10;
  }
  if ( v4 )
    LODWORD(v3) = CsrUnlockThread(v4);
  return v3;
}

```

## disassembly

```asm
0x180010e70  push    rbx
0x180010e72  sub     rsp, 20h
0x180010e76  or      eax, 0FFFFFFFFh
0x180010e79  mov     dword ptr [rdx], 0
0x180010e7f  mov     [rdx+4], eax
0x180010e82  mov     rbx, rdx
0x180010e85  mov     [rdx+8], eax
0x180010e88  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x180010e8d  mov     [rsp+28h+dwProcessId], 0
0x180010e95  mov     [rsp+28h+arg_10], 0
0x180010e9e  call    cs:__imp_GetWindowThreadProcessId
0x180010ea5  nop     dword ptr [rax+rax+00h]
0x180010eaa  test    eax, eax
0x180010eac  jz      short loc_180010F16
0x180010eae  movsxd  rdx, [rsp+28h+dwProcessId]
0x180010eb3  lea     r8, [rsp+28h+arg_10]
0x180010eb8  movsxd  rcx, eax
0x180010ebb  call    cs:__imp_CsrLockThreadByClientId
0x180010ec2  nop     dword ptr [rax+rax+00h]
0x180010ec7  test    eax, eax
0x180010ec9  js      short loc_180010F16
0x180010ecb  mov     rdx, [rsp+28h+arg_10]
0x180010ed0  movsxd  rax, [rsp+28h+dwProcessId]
0x180010ed5  mov     r8, [rdx+38h]
0x180010ed9  cmp     [r8], rax
0x180010edc  jnz     short loc_180010F1B
0x180010ede  lea     r10, [r8+20h]
0x180010ee2  xor     r9d, r9d
0x180010ee5  mov     rcx, [r10]
0x180010ee8  jmp     short loc_180010EF9
0x180010eea  lea     rax, [rcx-8]
0x180010eee  cmp     rax, rdx
0x180010ef1  jz      short loc_180010F00
0x180010ef3  mov     rcx, [rcx]
0x180010ef6  inc     r9d
0x180010ef9  cmp     rcx, r10
0x180010efc  jnz     short loc_180010EEA
0x180010efe  jmp     short loc_180010F1B
0x180010f00  mov     eax, [r8+78h]
0x180010f04  mov     [rbx], eax
0x180010f06  mov     rax, [rdx+38h]
0x180010f0a  mov     ecx, [rax+58h]
0x180010f0d  mov     [rbx+4], ecx
0x180010f10  mov     [rbx+8], r9d
0x180010f14  jmp     short loc_180010F1B
0x180010f16  mov     rdx, [rsp+28h+arg_10]
0x180010f1b  test    rdx, rdx
0x180010f1e  jz      short loc_180010F2F
0x180010f20  mov     rcx, rdx
0x180010f23  call    cs:__imp_CsrUnlockThread
0x180010f2a  nop     dword ptr [rax+rax+00h]
0x180010f2f  add     rsp, 20h
0x180010f33  pop     rbx
0x180010f34  retn
```
