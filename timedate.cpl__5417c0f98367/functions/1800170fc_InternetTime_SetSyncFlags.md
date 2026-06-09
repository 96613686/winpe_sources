# InternetTime_SetSyncFlags

- ea: `0x1800170fc`
- end: `0x180017184`
- name: `InternetTime_SetSyncFlags`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18001d370`

## callees

- `0x1800170fc`

## import_xrefs

- `SHLWAPI!SHSetValueW` at `0x18001716c`
- `SHLWAPI!SHSetValueW` at `0x18001716c`

## string_xrefs

- `0x18001715e`: `System\CurrentControlSet\Services\W32Time\Parameters`

## pseudocode

```c
LSTATUS __fastcall InternetTime_SetSyncFlags(int a1)
{
  int v1; // ecx
  const wchar_t *pvData; // rcx
  __int64 v3; // rax
  LSTATUS result; // eax

  if ( a1 )
  {
    v1 = a1 - 1;
    if ( v1 )
    {
      if ( v1 == 1 )
        pvData = L"NT5DS";
      else
        pvData = L"AllSync";
    }
    else
    {
      pvData = L"NTP";
    }
  }
  else
  {
    pvData = L"NoSync";
  }
  v3 = -1;
  do
    ++v3;
  while ( pvData[v3] );
  result = SHSetValueW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\W32Time\\Parameters",
             L"Type",
             1u,
             pvData,
             2 * v3 + 2);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800170fc  push    rbx
0x1800170fe  sub     rsp, 30h
0x180017102  xor     ebx, ebx
0x180017104  test    ecx, ecx
0x180017106  jz      short loc_18001712D
0x180017108  sub     ecx, 1
0x18001710b  jz      short loc_180017124
0x18001710d  cmp     ecx, 1
0x180017110  jz      short loc_18001711B
0x180017112  lea     rcx, aAllsync; "AllSync"
0x180017119  jmp     short loc_180017134
0x18001711b  lea     rcx, aNt5ds; "NT5DS"
0x180017122  jmp     short loc_180017134
0x180017124  lea     rcx, aNtp; "NTP"
0x18001712b  jmp     short loc_180017134
0x18001712d  lea     rcx, aNosync; "NoSync"
0x180017134  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017138  inc     rax
0x18001713b  cmp     [rcx+rax*2], bx
0x18001713f  jnz     short loc_180017138
0x180017141  lea     eax, ds:2[rax*2]
0x180017148  mov     r9d, 1; dwType
0x18001714e  mov     [rsp+38h+cbData], eax; cbData
0x180017152  lea     r8, aType; "Type"
0x180017159  mov     [rsp+38h+pvData], rcx; pvData
0x18001715e  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\W3"...
0x180017165  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001716c  call    cs:__imp_SHSetValueW
0x180017172  test    eax, eax
0x180017174  jle     short loc_18001717E
0x180017176  movzx   eax, ax
0x180017179  or      eax, 80070000h
0x18001717e  add     rsp, 30h
0x180017182  pop     rbx
0x180017183  retn
```
