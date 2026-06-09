# UpgradeNotificationRequired(void)

- ea: `0x180030478`
- end: `0x180030523`
- name: `?UpgradeNotificationRequired@@YAHXZ`
- size: `171`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033f10`

## callees

- `0x180030478`
- `0x1800306b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800304c2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800304c2`

## string_xrefs

- `0x1800304a6`: `SOFTWARE\Microsoft\Security Center\Svc\Upgrade`

## pseudocode

```c
_BOOL8 UpgradeNotificationRequired(void)
{
  __int64 v0; // r8
  __int64 v1; // rcx
  const char *v2; // r9
  DWORD v4; // [rsp+50h] [rbp+8h] BYREF
  __int64 v5; // [rsp+58h] [rbp+10h] BYREF

  v5 = 0;
  v4 = 8;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Security Center\\Svc\\Upgrade",
         L"UpgradeTime",
         0x40u,
         0,
         &v5,
         &v4) )
  {
    v1 = 0;
    v5 = 0;
  }
  else
  {
    v1 = v5;
  }
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v2 = "true";
    if ( !v1 )
      v2 = "false";
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), "false", v0, v2);
    v1 = v5;
  }
  return v1 != 0;
}

```

## disassembly

```asm
0x180030478  mov     r11, rsp
0x18003047b  sub     rsp, 48h
0x18003047f  lea     rax, [r11+8]
0x180030483  mov     qword ptr [r11+10h], 0
0x18003048b  mov     [r11-18h], rax
0x18003048f  lea     r8, aUpgradetime; "UpgradeTime"
0x180030496  lea     rax, [r11+10h]
0x18003049a  mov     [rsp+48h+arg_0], 8
0x1800304a2  mov     [r11-20h], rax
0x1800304a6  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Security Center\\S"...
0x1800304ad  mov     r9d, 40h ; '@'; dwFlags
0x1800304b3  mov     qword ptr [r11-28h], 0
0x1800304bb  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800304c2  call    cs:__imp_RegGetValueW
0x1800304c8  test    eax, eax
0x1800304ca  jz      short loc_1800304D5
0x1800304cc  xor     ecx, ecx
0x1800304ce  mov     [rsp+48h+arg_8], rcx
0x1800304d3  jmp     short loc_1800304DA
0x1800304d5  mov     rcx, [rsp+48h+arg_8]
0x1800304da  mov     rax, cs:WPP_GLOBAL_Control
0x1800304e1  lea     rdx, WPP_GLOBAL_Control
0x1800304e8  cmp     rax, rdx
0x1800304eb  jz      short loc_180030516
0x1800304ed  test    byte ptr [rax+1Ch], 4
0x1800304f1  jz      short loc_180030516
0x1800304f3  test    rcx, rcx
0x1800304f6  lea     rdx, aFalse; "false"
0x1800304fd  mov     rcx, [rax+10h]
0x180030501  lea     r9, aTrue_0; "true"
0x180030508  cmovz   r9, rdx
0x18003050c  call    WPP_SF_s
0x180030511  mov     rcx, [rsp+48h+arg_8]
0x180030516  xor     eax, eax
0x180030518  test    rcx, rcx
0x18003051b  setnz   al
0x18003051e  add     rsp, 48h
0x180030522  retn
```
