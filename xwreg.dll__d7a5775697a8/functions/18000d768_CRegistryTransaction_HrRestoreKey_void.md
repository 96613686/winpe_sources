# CRegistryTransaction::HrRestoreKey(void)

- ea: `0x18000d768`
- end: `0x18000d852`
- name: `?HrRestoreKey@CRegistryTransaction@@QEAAJXZ`
- size: `234`
- prototype: `__int64 __fastcall(CRegistryTransaction *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d68c`

## callees

- `0x180007820`
- `0x18000d768`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyW` at `0x18000d804`
- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyW` at `0x18000d804`

## pseudocode

```c
__int64 __fastcall CRegistryTransaction::HrRestoreKey(CRegistryTransaction *this)
{
  __int64 v1; // r9
  HKEY v4; // rcx
  LSTATUS v5; // eax
  unsigned int v6; // ebx

  v1 = *((unsigned int *)this + 136);
  if ( (int)v1 >= 0 )
  {
    v4 = (HKEY)*((_QWORD *)this + 67);
    if ( v4 )
    {
      v5 = RegRestoreKeyW(v4, (LPCWSTR)this + 4, 0);
      v6 = v5;
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_b6864e106af034a19631ace060353c02_Traceguids, v6);
      return v6;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_b6864e106af034a19631ace060353c02_Traceguids, 2147483658LL);
      return 2147483658LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_b6864e106af034a19631ace060353c02_Traceguids, v1);
    return *((unsigned int *)this + 136);
  }
}

```

## disassembly

```asm
0x18000d768  push    rbx
0x18000d76a  sub     rsp, 20h
0x18000d76e  mov     r9d, [rcx+220h]
0x18000d775  mov     rbx, rcx
0x18000d778  test    r9d, r9d
0x18000d77b  jns     short loc_18000D7B6
0x18000d77d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d784  lea     rax, WPP_GLOBAL_Control
0x18000d78b  cmp     rcx, rax
0x18000d78e  jz      short loc_18000D7AB
0x18000d790  test    byte ptr [rcx+1Ch], 4
0x18000d794  jz      short loc_18000D7AB
0x18000d796  mov     rcx, [rcx+10h]
0x18000d79a  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d7a1  mov     edx, 10h
0x18000d7a6  call    WPP_SF_D
0x18000d7ab  mov     eax, [rbx+220h]
0x18000d7b1  jmp     loc_18000D84C
0x18000d7b6  mov     rcx, [rcx+218h]; hKey
0x18000d7bd  test    rcx, rcx
0x18000d7c0  jnz     short loc_18000D7FD
0x18000d7c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7c9  lea     rax, WPP_GLOBAL_Control
0x18000d7d0  cmp     rcx, rax
0x18000d7d3  jz      short loc_18000D7F6
0x18000d7d5  test    byte ptr [rcx+1Ch], 4
0x18000d7d9  jz      short loc_18000D7F6
0x18000d7db  mov     rcx, [rcx+10h]
0x18000d7df  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d7e6  mov     edx, 11h
0x18000d7eb  mov     r9d, 8000000Ah
0x18000d7f1  call    WPP_SF_D
0x18000d7f6  mov     eax, 8000000Ah
0x18000d7fb  jmp     short loc_18000D84C
0x18000d7fd  lea     rdx, [rbx+8]; lpFile
0x18000d801  xor     r8d, r8d; dwFlags
0x18000d804  call    cs:__imp_RegRestoreKeyW
0x18000d80a  mov     ebx, eax
0x18000d80c  test    eax, eax
0x18000d80e  jle     short loc_18000D819
0x18000d810  movzx   ebx, ax
0x18000d813  or      ebx, 80070000h
0x18000d819  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d820  lea     rax, WPP_GLOBAL_Control
0x18000d827  cmp     rcx, rax
0x18000d82a  jz      short loc_18000D84A
0x18000d82c  test    byte ptr [rcx+1Ch], 10h
0x18000d830  jz      short loc_18000D84A
0x18000d832  mov     rcx, [rcx+10h]
0x18000d836  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d83d  mov     edx, 12h
0x18000d842  mov     r9d, ebx
0x18000d845  call    WPP_SF_D
0x18000d84a  mov     eax, ebx
0x18000d84c  add     rsp, 20h
0x18000d850  pop     rbx
0x18000d851  retn
```
