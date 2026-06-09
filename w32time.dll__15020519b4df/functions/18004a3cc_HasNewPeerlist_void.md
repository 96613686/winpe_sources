# HasNewPeerlist(void)

- ea: `0x18004a3cc`
- end: `0x18004a46d`
- name: `?HasNewPeerlist@@YAHXZ`
- size: `161`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180049fd0`
- `0x18004afd0`
- `0x18004b2f0`

## callees

- `0x180049bf4`
- `0x18004a3cc`
- `0x18004f5d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004a438`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004a438`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a457`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a457`

## string_xrefs

- `0x18004a42d`: `time.windows.com,0x8`
- `0x18004a424`: `time.windows.com,0x9`

## pseudocode

```c
__int64 HasNewPeerlist(void)
{
  int Role; // eax
  int v1; // esi
  unsigned int v2; // edi
  const wchar_t *v3; // rcx
  int v5; // [rsp+40h] [rbp+8h] BYREF
  int v6; // [rsp+48h] [rbp+10h] BYREF
  int v7; // [rsp+50h] [rbp+18h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp+20h] BYREF

  hMem = 0;
  v7 = 0;
  v6 = 0;
  v5 = 0;
  Role = GetRole((enum RoleType *)&v6, &v5);
  v1 = v5;
  if ( Role < 0 )
    v1 = 0;
  v2 = 0;
  if ( !(unsigned int)ReadNtpServerFromParametersKey(&hMem, &v7) )
  {
    v3 = L"time.windows.com,0x8";
    if ( !v1 )
      v3 = L"time.windows.com,0x9";
    LOBYTE(v2) = (unsigned int)_o__wcsicmp(v3, hMem) != 0;
  }
  if ( hMem )
    LocalFree(hMem);
  return v2;
}

```

## disassembly

```asm
0x18004a3cc  mov     rax, rsp
0x18004a3cf  push    rsi
0x18004a3d0  push    rdi
0x18004a3d1  sub     rsp, 28h
0x18004a3d5  lea     rdx, [rax+8]; int *
0x18004a3d9  mov     qword ptr [rax+20h], 0
0x18004a3e1  lea     rcx, [rax+10h]; enum RoleType *
0x18004a3e5  mov     dword ptr [rax+18h], 0
0x18004a3ec  mov     dword ptr [rax+10h], 0
0x18004a3f3  mov     dword ptr [rax+8], 0
0x18004a3fa  call    ?GetRole@@YAJPEAW4RoleType@@PEAH@Z; GetRole(RoleType *,int *)
0x18004a3ff  mov     esi, [rsp+38h+arg_0]
0x18004a403  lea     rdx, [rsp+38h+arg_10]
0x18004a408  xor     ecx, ecx
0x18004a40a  test    eax, eax
0x18004a40c  cmovs   esi, ecx
0x18004a40f  lea     rcx, [rsp+38h+hMem]
0x18004a414  xor     edi, edi
0x18004a416  call    ReadNtpServerFromParametersKey
0x18004a41b  test    eax, eax
0x18004a41d  jnz     short loc_18004A44A
0x18004a41f  mov     rdx, [rsp+38h+hMem]
0x18004a424  lea     rax, aTimeWindowsCom; "time.windows.com,0x9"
0x18004a42b  test    esi, esi
0x18004a42d  lea     rcx, aTimeWindowsCom_0; "time.windows.com,0x8"
0x18004a434  cmovz   rcx, rax
0x18004a438  call    cs:__imp__o__wcsicmp
0x18004a43f  nop     dword ptr [rax+rax+00h]
0x18004a444  test    eax, eax
0x18004a446  setnz   dil
0x18004a44a  cmp     [rsp+38h+hMem], 0
0x18004a450  jz      short loc_18004A463
0x18004a452  mov     rcx, [rsp+38h+hMem]; hMem
0x18004a457  call    cs:__imp_LocalFree
0x18004a45e  nop     dword ptr [rax+rax+00h]
0x18004a463  mov     eax, edi
0x18004a465  add     rsp, 28h
0x18004a469  pop     rdi
0x18004a46a  pop     rsi
0x18004a46b  retn
```
