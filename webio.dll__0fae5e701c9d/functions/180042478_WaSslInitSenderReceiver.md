# WaSslInitSenderReceiver

- ea: `0x180042478`
- end: `0x180042625`
- name: `WaSslInitSenderReceiver`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180042414`

## callees

- `0x180042478`
- `0x18004262c`
- `0x1800722f0`
- `0x18009218c`
- `0x1800971ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800424e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180042536`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800424e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180042536`

## string_xrefs

- `0x1800424b9`: `LookasideDepth`

## pseudocode

```c
void WaSslInitSenderReceiver()
{
  __int64 v0; // r9
  int v1; // eax
  unsigned int pvData; // [rsp+40h] [rbp-10h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-Ch] BYREF

  pvData = 0;
  pcbData = 4;
  if ( !WaSslSenderReceiverInitialized )
  {
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\WinHttp",
            L"LookasideDepth",
            0x10u,
            0,
            &pvData,
            &pcbData) )
    {
      v0 = pvData;
      if ( pvData < 0x20 )
      {
        v0 = 32;
        pvData = 32;
      }
      WaSslLookasideMaxDepth = v0;
      if ( (xmmword_1800AD720 & 8) != 0 )
        WPP_SF_d(1027, 56, WPP_56419e6f729131a1bc9745be6fd81bf0_Traceguids, v0);
    }
    WaInitializeLookaside();
    pcbData = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\WinHttp",
           L"SslSenderChunkKbSize",
           0x10u,
           0,
           &pvData,
           &pcbData) )
    {
      goto LABEL_4;
    }
    v1 = pvData;
    if ( pvData >= 4 )
    {
      if ( pvData <= 0x20 )
        goto LABEL_17;
      v1 = 32;
    }
    else
    {
      v1 = 4;
    }
    pvData = v1;
LABEL_17:
    dword_1800AD564 = v1 << 10;
    if ( (xmmword_1800AD720 & 8) != 0 )
      WPP_SF_dd(1027, 57, WPP_56419e6f729131a1bc9745be6fd81bf0_Traceguids, (unsigned int)(v1 << 10), v1);
LABEL_4:
    WaSslSenderReceiverInitialized = 1;
    return;
  }
  if ( (xmmword_1800AD720 & 8) != 0 )
    WPP_SF_d(1027, 55, WPP_56419e6f729131a1bc9745be6fd81bf0_Traceguids, (unsigned int)dword_1800AD564);
}

```

## disassembly

```asm
0x180042478  push    rbp
0x18004247a  mov     rbp, rsp
0x18004247d  sub     rsp, 50h
0x180042481  mov     rax, cs:__security_cookie
0x180042488  xor     rax, rsp
0x18004248b  mov     [rbp+var_8], rax
0x18004248f  cmp     cs:WaSslSenderReceiverInitialized, 0
0x180042496  mov     [rbp+var_10], 0
0x18004249d  mov     [rbp+var_C], 4
0x1800424a4  jnz     loc_180042564
0x1800424aa  lea     rax, [rbp+var_C]
0x1800424ae  mov     r9d, 10h; dwFlags
0x1800424b4  mov     [rsp+50h+pcbData], rax; pcbData
0x1800424b9  lea     r8, Value; "LookasideDepth"
0x1800424c0  lea     rax, [rbp+var_10]
0x1800424c4  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800424cb  mov     [rsp+50h+pvData], rax; pvData
0x1800424d0  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800424d7  mov     [rsp+50h+pdwType], 0; pdwType
0x1800424e0  call    cs:__imp_RegGetValueW
0x1800424e7  nop     dword ptr [rax+rax+00h]
0x1800424ec  test    eax, eax
0x1800424ee  jz      loc_18004258C
0x1800424f4  call    WaInitializeLookaside
0x1800424f9  lea     rax, [rbp+var_C]
0x1800424fd  mov     [rbp+var_C], 4
0x180042504  mov     [rsp+50h+pcbData], rax; pcbData
0x180042509  lea     r8, aSslsenderchunk; "SslSenderChunkKbSize"
0x180042510  lea     rax, [rbp+var_10]
0x180042514  mov     r9d, 10h; dwFlags
0x18004251a  mov     [rsp+50h+pvData], rax; pvData
0x18004251f  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180042526  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18004252d  mov     [rsp+50h+pdwType], 0; pdwType
0x180042536  call    cs:__imp_RegGetValueW
0x18004253d  nop     dword ptr [rax+rax+00h]
0x180042542  test    eax, eax
0x180042544  jz      loc_1800425CF
0x18004254a  mov     cs:WaSslSenderReceiverInitialized, 1
0x180042551  mov     rcx, [rbp+var_8]
0x180042555  xor     rcx, rsp; StackCookie
0x180042558  call    __security_check_cookie
0x18004255d  add     rsp, 50h
0x180042561  pop     rbp
0x180042562  retn
0x180042564  test    byte ptr cs:xmmword_1800AD720, 8
0x18004256b  jz      short loc_180042551
0x18004256d  mov     r9d, cs:dword_1800AD564
0x180042574  lea     r8, WPP_56419e6f729131a1bc9745be6fd81bf0_Traceguids
0x18004257b  mov     edx, 37h ; '7'
0x180042580  mov     ecx, 403h
0x180042585  call    WPP_SF_d
0x18004258a  jmp     short loc_180042551
0x18004258c  mov     r9d, [rbp+var_10]
0x180042590  cmp     r9d, 20h ; ' '
0x180042594  jnb     short loc_1800425A0
0x180042596  mov     r9d, 20h ; ' '
0x18004259c  mov     [rbp+var_10], r9d
0x1800425a0  mov     cs:WaSslLookasideMaxDepth, r9d
0x1800425a7  test    byte ptr cs:xmmword_1800AD720, 8
0x1800425ae  jz      loc_1800424F4
0x1800425b4  mov     edx, 38h ; '8'
0x1800425b9  lea     r8, WPP_56419e6f729131a1bc9745be6fd81bf0_Traceguids
0x1800425c0  mov     ecx, 403h
0x1800425c5  call    WPP_SF_d
0x1800425ca  jmp     loc_1800424F4
0x1800425cf  mov     eax, [rbp+var_10]
0x1800425d2  cmp     eax, 4
0x1800425d5  jnb     short loc_1800425DE
0x1800425d7  mov     eax, 4
0x1800425dc  jmp     short loc_1800425E8
0x1800425de  cmp     eax, 20h ; ' '
0x1800425e1  jbe     short loc_1800425EB
0x1800425e3  mov     eax, 20h ; ' '
0x1800425e8  mov     [rbp+var_10], eax
0x1800425eb  mov     r9d, eax
0x1800425ee  shl     r9d, 0Ah
0x1800425f2  mov     cs:dword_1800AD564, r9d
0x1800425f9  test    byte ptr cs:xmmword_1800AD720, 8
0x180042600  jz      loc_18004254A
0x180042606  mov     edx, 39h ; '9'
0x18004260b  mov     dword ptr [rsp+50h+pdwType], eax
0x18004260f  mov     ecx, 403h
0x180042614  lea     r8, WPP_56419e6f729131a1bc9745be6fd81bf0_Traceguids
0x18004261b  call    WPP_SF_dd
0x180042620  jmp     loc_18004254A
```
