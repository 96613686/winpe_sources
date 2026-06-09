# CRegistryTransaction::CRegistryTransaction(void)

- ea: `0x18000d070`
- end: `0x18000d1e6`
- name: `??0CRegistryTransaction@@QEAA@XZ`
- size: `374`
- prototype: `CRegistryTransaction *__fastcall(CRegistryTransaction *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000cf6c`

## callees

- `0x180003b90`
- `0x180007820`
- `0x18000a9d4`
- `0x18000abbc`
- `0x18000d070`
- `0x1800127d6`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18000d0d8`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18000d0d8`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18000d14b`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18000d14b`

## pseudocode

```c
CRegistryTransaction *__fastcall CRegistryTransaction::CRegistryTransaction(CRegistryTransaction *this)
{
  unsigned int LastErrorHRESULT; // eax
  int v3; // eax
  PVOID *v4; // rcx
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x20Au);
  *((_DWORD *)this + 136) = 0;
  *((_WORD *)this + 4) = 0;
  *((_QWORD *)this + 67) = 0;
  *(_QWORD *)this = L"$XW_RL_";
  if ( !GetTempPathW(0x105u, Buffer) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      LastErrorHRESULT = GetLastErrorHRESULT();
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_b6864e106af034a19631ace060353c02_Traceguids,
        LastErrorHRESULT);
    }
    Buffer[0] = 0;
    StringCchCopyW(Buffer, 0x105u, L".");
  }
  if ( GetTempFileNameW(Buffer, *(LPCWSTR *)this, 0, (LPWSTR)this + 4) )
    goto LABEL_10;
  v3 = GetLastErrorHRESULT();
  *((_DWORD *)this + 136) = v3;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return this;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)WPP_b6864e106af034a19631ace060353c02_Traceguids,
      (unsigned int)Buffer,
      v3);
LABEL_10:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x10) != 0 )
    WPP_SF_D(v4[2], 12, WPP_b6864e106af034a19631ace060353c02_Traceguids, *((unsigned int *)this + 136));
  return this;
}

```

## disassembly

```asm
0x18000d070  mov     [rsp+arg_8], rbx
0x18000d075  mov     [rsp+arg_10], rsi
0x18000d07a  push    rdi
0x18000d07b  sub     rsp, 250h
0x18000d082  mov     rax, cs:__security_cookie
0x18000d089  xor     rax, rsp
0x18000d08c  mov     [rsp+258h+var_18], rax
0x18000d094  mov     rbx, rcx
0x18000d097  xor     edx, edx; Val
0x18000d099  lea     rcx, [rsp+258h+Buffer]; void *
0x18000d09e  mov     r8d, 20Ah; Size
0x18000d0a4  call    memset_0
0x18000d0a9  xor     eax, eax
0x18000d0ab  mov     dword ptr [rbx+220h], 0
0x18000d0b5  mov     [rbx+8], ax
0x18000d0b9  lea     rdx, [rsp+258h+Buffer]; lpBuffer
0x18000d0be  lea     rax, aXwRl; "$XW_RL_"
0x18000d0c5  mov     qword ptr [rbx+218h], 0
0x18000d0d0  mov     ecx, 105h; nBufferLength
0x18000d0d5  mov     [rbx], rax
0x18000d0d8  call    cs:__imp_GetTempPathW
0x18000d0de  lea     rsi, WPP_GLOBAL_Control
0x18000d0e5  test    eax, eax
0x18000d0e7  jnz     short loc_18000D13C
0x18000d0e9  mov     rax, cs:WPP_GLOBAL_Control
0x18000d0f0  cmp     rax, rsi
0x18000d0f3  jz      short loc_18000D11F
0x18000d0f5  test    byte ptr [rax+1Ch], 10h
0x18000d0f9  jz      short loc_18000D11F
0x18000d0fb  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000d100  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d107  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d10e  mov     edx, 0Ah
0x18000d113  mov     r9d, eax
0x18000d116  mov     rcx, [rcx+10h]
0x18000d11a  call    WPP_SF_D
0x18000d11f  xor     eax, eax
0x18000d121  lea     r8, asc_180016F18; "."
0x18000d128  mov     edx, 105h; unsigned __int64
0x18000d12d  mov     [rsp+258h+Buffer], ax
0x18000d132  lea     rcx, [rsp+258h+Buffer]; unsigned __int16 *
0x18000d137  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d13c  mov     rdx, [rbx]; lpPrefixString
0x18000d13f  lea     r9, [rbx+8]; lpTempFileName
0x18000d143  xor     r8d, r8d; uUnique
0x18000d146  lea     rcx, [rsp+258h+Buffer]; lpPathName
0x18000d14b  call    cs:__imp_GetTempFileNameW
0x18000d151  test    eax, eax
0x18000d153  jnz     short loc_18000D190
0x18000d155  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000d15a  mov     [rbx+220h], eax
0x18000d160  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d167  cmp     rcx, rsi
0x18000d16a  jz      short loc_18000D1BE
0x18000d16c  test    byte ptr [rcx+1Ch], 4
0x18000d170  jz      short loc_18000D197
0x18000d172  mov     rcx, [rcx+10h]
0x18000d176  lea     r9, [rsp+258h+Buffer]
0x18000d17b  mov     edx, 0Bh
0x18000d180  mov     [rsp+258h+var_238], eax
0x18000d184  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d18b  call    WPP_SF_SD
0x18000d190  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d197  cmp     rcx, rsi
0x18000d19a  jz      short loc_18000D1BE
0x18000d19c  test    byte ptr [rcx+1Ch], 10h
0x18000d1a0  jz      short loc_18000D1BE
0x18000d1a2  mov     r9d, [rbx+220h]
0x18000d1a9  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d1b0  mov     rcx, [rcx+10h]
0x18000d1b4  mov     edx, 0Ch
0x18000d1b9  call    WPP_SF_D
0x18000d1be  mov     rax, rbx
0x18000d1c1  mov     rcx, [rsp+258h+var_18]
0x18000d1c9  xor     rcx, rsp; StackCookie
0x18000d1cc  call    __security_check_cookie
0x18000d1d1  lea     r11, [rsp+258h+var_8]
0x18000d1d9  mov     rbx, [r11+18h]
0x18000d1dd  mov     rsi, [r11+20h]
0x18000d1e1  mov     rsp, r11
0x18000d1e4  pop     rdi
0x18000d1e5  retn
```
