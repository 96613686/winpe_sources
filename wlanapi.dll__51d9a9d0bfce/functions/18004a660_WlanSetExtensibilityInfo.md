# WlanSetExtensibilityInfo

- ea: `0x18004a660`
- end: `0x18004a83a`
- name: `WlanSetExtensibilityInfo`
- size: `474`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800063a0`
- `0x180019a20`
- `0x18004960c`
- `0x18004a660`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a6c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a7ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a6c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a7ce`
- `DEVOBJ!DevObjGetClassDevs` at `0x18004a739`
- `DEVOBJ!DevObjGetClassDevs` at `0x18004a739`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18004a6b3`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18004a6b3`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18004a7c4`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18004a7c4`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18004a810`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18004a810`

## pseudocode

```c
__int64 __fastcall WlanSetExtensibilityInfo(_QWORD *a1, __int64 a2)
{
  __int64 DeviceInfoList; // rdi
  DWORD v5; // eax
  unsigned int ExtensibleIfMatch; // ebx
  DWORD LastError; // eax
  unsigned int v8; // esi
  __int64 v9; // rcx
  _BYTE *v10; // rax
  int v12; // [rsp+30h] [rbp-58h] BYREF
  _OWORD v13[3]; // [rsp+38h] [rbp-50h] BYREF

  v12 = 0;
  memset(v13, 0, sizeof(v13));
  DeviceInfoList = DevObjCreateDeviceInfoList(&GUID_DEVCLASS_NET, 0, 0, 0, 0);
  if ( DeviceInfoList == -1 && (v5 = GetLastError(), (ExtensibleIfMatch = v5) != 0) )
  {
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids, v5);
    }
  }
  else
  {
    if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVCLASS_NET, 0, 2, 0, 0)
      || (LastError = GetLastError(), (ExtensibleIfMatch = LastError) == 0) )
    {
      v8 = 0;
      do
      {
        v9 = 48;
        v10 = v13;
        do
        {
          *v10++ = 0;
          --v9;
        }
        while ( v9 );
        LODWORD(v13[0]) = 48;
        if ( (unsigned int)DevObjEnumDeviceInfo(DeviceInfoList, v8, v13) )
        {
          ExtensibleIfMatch = MakeExtensibleIfMatch(DeviceInfoList, (__int64)v13, a1, a2, &v12);
        }
        else
        {
          ExtensibleIfMatch = GetLastError();
          if ( ExtensibleIfMatch == 259 )
            break;
        }
        ++v8;
      }
      while ( !v12 );
    }
    else if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25)
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids, LastError);
    }
    if ( DeviceInfoList != -1 )
      DevObjDestroyDeviceInfoList(DeviceInfoList);
  }
  return ExtensibleIfMatch;
}

```

## disassembly

```asm
0x18004a660  mov     [rsp+arg_10], rbx
0x18004a665  mov     [rsp+arg_18], rbp
0x18004a66a  push    rsi
0x18004a66b  push    rdi
0x18004a66c  push    r14
0x18004a66e  sub     rsp, 70h
0x18004a672  mov     rax, cs:__security_cookie
0x18004a679  xor     rax, rsp
0x18004a67c  mov     [rsp+88h+var_20], rax
0x18004a681  xorps   xmm0, xmm0
0x18004a684  mov     r14, rdx
0x18004a687  mov     rbp, rcx
0x18004a68a  xor     ebx, ebx
0x18004a68c  xor     edx, edx
0x18004a68e  mov     [rsp+88h+var_58], ebx
0x18004a692  lea     rcx, GUID_DEVCLASS_NET
0x18004a699  mov     [rsp+88h+var_68], rbx
0x18004a69e  xor     r9d, r9d
0x18004a6a1  xor     r8d, r8d
0x18004a6a4  movups  [rsp+88h+var_50], xmm0
0x18004a6a9  movups  [rsp+88h+var_40], xmm0
0x18004a6ae  movups  [rsp+88h+var_30], xmm0
0x18004a6b3  call    cs:__imp_DevObjCreateDeviceInfoList
0x18004a6b9  mov     rdi, rax
0x18004a6bc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004a6c0  jnz     short loc_18004A714
0x18004a6c2  call    cs:__imp_GetLastError
0x18004a6c8  mov     ebx, eax
0x18004a6ca  test    eax, eax
0x18004a6cc  jz      short loc_18004A714
0x18004a6ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a6d5  lea     rdx, WPP_GLOBAL_Control
0x18004a6dc  cmp     rcx, rdx
0x18004a6df  jz      loc_18004A816
0x18004a6e5  cmp     byte ptr [rcx+19h], 1
0x18004a6e9  jb      loc_18004A816
0x18004a6ef  test    byte ptr [rcx+1Ch], 1
0x18004a6f3  jz      loc_18004A816
0x18004a6f9  mov     rcx, [rcx+10h]
0x18004a6fd  lea     edx, [rdi+30h]
0x18004a700  mov     r9d, eax
0x18004a703  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x18004a70a  call    WPP_SF_d
0x18004a70f  jmp     loc_18004A816
0x18004a714  mov     [rsp+88h+var_60], 0
0x18004a71d  lea     rdx, GUID_DEVCLASS_NET
0x18004a724  mov     r9d, 2
0x18004a72a  mov     [rsp+88h+var_68], 0
0x18004a733  xor     r8d, r8d
0x18004a736  mov     rcx, rdi
0x18004a739  call    cs:__imp_DevObjGetClassDevs
0x18004a73f  test    eax, eax
0x18004a741  jnz     short loc_18004A794
0x18004a743  call    cs:__imp_GetLastError
0x18004a749  mov     ebx, eax
0x18004a74b  test    eax, eax
0x18004a74d  jz      short loc_18004A794
0x18004a74f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a756  lea     rdx, WPP_GLOBAL_Control
0x18004a75d  cmp     rcx, rdx
0x18004a760  jz      loc_18004A807
0x18004a766  cmp     byte ptr [rcx+19h], 1
0x18004a76a  jb      loc_18004A807
0x18004a770  test    byte ptr [rcx+1Ch], 1
0x18004a774  jz      loc_18004A807
0x18004a77a  mov     rcx, [rcx+10h]
0x18004a77e  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x18004a785  mov     edx, 30h ; '0'
0x18004a78a  mov     r9d, eax
0x18004a78d  call    WPP_SF_d
0x18004a792  jmp     short loc_18004A807
0x18004a794  xor     esi, esi
0x18004a796  cmp     [rsp+88h+var_58], esi
0x18004a79a  jnz     short loc_18004A807
0x18004a79c  mov     ecx, 30h ; '0'
0x18004a7a1  lea     rax, [rsp+88h+var_50]
0x18004a7a6  mov     byte ptr [rax], 0
0x18004a7a9  inc     rax
0x18004a7ac  sub     rcx, 1
0x18004a7b0  jnz     short loc_18004A7A6
0x18004a7b2  lea     r8, [rsp+88h+var_50]
0x18004a7b7  mov     dword ptr [rsp+88h+var_50], 30h ; '0'
0x18004a7bf  mov     edx, esi
0x18004a7c1  mov     rcx, rdi
0x18004a7c4  call    cs:__imp_DevObjEnumDeviceInfo
0x18004a7ca  test    eax, eax
0x18004a7cc  jnz     short loc_18004A7DF
0x18004a7ce  call    cs:__imp_GetLastError
0x18004a7d4  mov     ebx, eax
0x18004a7d6  cmp     eax, 103h
0x18004a7db  jz      short loc_18004A807
0x18004a7dd  jmp     short loc_18004A7FE
0x18004a7df  lea     rax, [rsp+88h+var_58]
0x18004a7e4  mov     r9, r14
0x18004a7e7  mov     r8, rbp
0x18004a7ea  mov     [rsp+88h+var_68], rax
0x18004a7ef  lea     rdx, [rsp+88h+var_50]
0x18004a7f4  mov     rcx, rdi
0x18004a7f7  call    MakeExtensibleIfMatch
0x18004a7fc  mov     ebx, eax
0x18004a7fe  inc     esi
0x18004a800  cmp     [rsp+88h+var_58], 0
0x18004a805  jz      short loc_18004A79C
0x18004a807  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18004a80b  jz      short loc_18004A816
0x18004a80d  mov     rcx, rdi
0x18004a810  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18004a816  mov     eax, ebx
0x18004a818  mov     rcx, [rsp+88h+var_20]
0x18004a81d  xor     rcx, rsp; StackCookie
0x18004a820  call    __security_check_cookie
0x18004a825  lea     r11, [rsp+88h+var_18]
0x18004a82a  mov     rbx, [r11+30h]
0x18004a82e  mov     rbp, [r11+38h]
0x18004a832  mov     rsp, r11
0x18004a835  pop     r14
0x18004a837  pop     rdi
0x18004a838  pop     rsi
0x18004a839  retn
```
