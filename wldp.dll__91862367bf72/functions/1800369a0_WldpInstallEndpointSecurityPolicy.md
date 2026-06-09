# WldpInstallEndpointSecurityPolicy

- ea: `0x1800369a0`
- end: `0x180036b96`
- name: `WldpInstallEndpointSecurityPolicy`
- size: `502`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001f038`
- `0x1800206f4`
- `0x18002d870`
- `0x180035cdc`
- `0x180035f90`
- `0x18003611c`
- `0x1800362dc`
- `0x1800369a0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036aac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036b1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036b6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036aac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036b1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036b6b`
- `ntdll!NtQuerySystemInformationEx` at `0x180036ade`
- `ntdll!NtQuerySystemInformationEx` at `0x180036ade`
- `ntdll!RtlFreeUnicodeString` at `0x180036a48`
- `ntdll!RtlFreeUnicodeString` at `0x180036a94`
- `ntdll!RtlFreeUnicodeString` at `0x180036b06`
- `ntdll!RtlFreeUnicodeString` at `0x180036b54`
- `ntdll!RtlFreeUnicodeString` at `0x180036b79`
- `ntdll!RtlFreeUnicodeString` at `0x180036a48`
- `ntdll!RtlFreeUnicodeString` at `0x180036a94`
- `ntdll!RtlFreeUnicodeString` at `0x180036b06`
- `ntdll!RtlFreeUnicodeString` at `0x180036b54`
- `ntdll!RtlFreeUnicodeString` at `0x180036b79`

## string_xrefs

- `0x180036a32`: `onecore\base\ngscb\wldp\dll\endpointsecuritypolicy.cpp`
- `0x180036a7e`: `onecore\base\ngscb\wldp\dll\endpointsecuritypolicy.cpp`
- `0x180036aef`: `onecore\base\ngscb\wldp\dll\endpointsecuritypolicy.cpp`
- `0x180036b38`: `onecore\base\ngscb\wldp\dll\endpointsecuritypolicy.cpp`

## pseudocode

```c
__int64 __fastcall WldpInstallEndpointSecurityPolicy(__int64 a1, __int64 a2, _QWORD *a3)
{
  int v6; // eax
  unsigned int v7; // edi
  int v9; // eax
  unsigned int v10; // ebx
  HLOCAL v11; // rcx
  HLOCAL v12; // rbx
  int v13; // eax
  unsigned int v14; // edi
  int v15; // [rsp+20h] [rbp-48h]
  HLOCAL hMem; // [rsp+38h] [rbp-30h] BYREF
  __int64 v17; // [rsp+40h] [rbp-28h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]
  unsigned int v20; // [rsp+90h] [rbp+28h] BYREF

  hMem = 0;
  UnicodeString = 0;
  v20 = 0;
  v17 = 0;
  if ( a1 && a2 && a3 && (unsigned __int8)IsValidEndpointSecPath() && (unsigned __int8)IsValidIdentityEku(a2) )
  {
    *a3 = 0;
    v6 = ConvertPathToDevicePath(a1, &UnicodeString);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v9 = SetupBuffer(0, &UnicodeString, a2, &v20);
      v10 = v9;
      if ( v9 >= 0 )
      {
        v12 = hMem;
        v13 = NtQuerySystemInformationEx(256, hMem, v20, &v17);
        if ( v13 >= 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xF5,
            (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\endpointsecuritypolicy.cpp",
            (const char *)0x8000FFFFLL,
            8);
          *a3 = v17;
          RtlFreeUnicodeString(&UnicodeString);
          hMem = 0;
          if ( v12 )
            LocalFree(v12);
          return 0;
        }
        else
        {
          v14 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0xF3,
                  (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\endpointsecuritypolicy.cpp",
                  (const char *)(unsigned int)v13,
                  8);
          RtlFreeUnicodeString(&UnicodeString);
          hMem = 0;
          if ( v12 )
            LocalFree(v12);
          return v14;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEC,
          (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\endpointsecuritypolicy.cpp",
          (const char *)(unsigned int)v9,
          (int)&hMem);
        RtlFreeUnicodeString(&UnicodeString);
        v11 = hMem;
        hMem = 0;
        if ( v11 )
          LocalFree(v11);
        return v10;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE6,
        (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\endpointsecuritypolicy.cpp",
        (const char *)(unsigned int)v6,
        v15);
      RtlFreeUnicodeString(&UnicodeString);
      return v7;
    }
  }
  else
  {
    RtlFreeUnicodeString(&UnicodeString);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800369a0  push    rbp
0x1800369a2  push    rbx
0x1800369a3  push    rsi
0x1800369a4  push    rdi
0x1800369a5  mov     rbp, rsp
0x1800369a8  sub     rsp, 68h
0x1800369ac  mov     rsi, r8
0x1800369af  mov     rbx, rdx
0x1800369b2  mov     rdi, rcx
0x1800369b5  mov     [rbp+hMem], 0
0x1800369bd  xorps   xmm0, xmm0
0x1800369c0  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x1800369c4  mov     [rbp+arg_0], 0
0x1800369cb  mov     [rbp+var_28], 0
0x1800369d3  mov     [rbp+var_38], 0
0x1800369da  test    rcx, rcx
0x1800369dd  jz      loc_180036B75
0x1800369e3  test    rdx, rdx
0x1800369e6  jz      loc_180036B75
0x1800369ec  test    r8, r8
0x1800369ef  jz      loc_180036B75
0x1800369f5  call    IsValidEndpointSecPath
0x1800369fa  test    al, al
0x1800369fc  jz      loc_180036B75
0x180036a02  mov     rcx, rbx
0x180036a05  call    IsValidIdentityEku
0x180036a0a  test    al, al
0x180036a0c  jz      loc_180036B75
0x180036a12  mov     qword ptr [rsi], 0
0x180036a19  lea     rdx, [rbp+UnicodeString]
0x180036a1d  mov     rcx, rdi
0x180036a20  call    ConvertPathToDevicePath
0x180036a25  mov     edi, eax
0x180036a27  test    eax, eax
0x180036a29  jns     short loc_180036A56
0x180036a2b  mov     rcx, [rbp+20h]; this
0x180036a2f  mov     r9d, eax; char *
0x180036a32  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\wldp\\dll\\endpoi"...
0x180036a39  mov     edx, 0E6h; void *
0x180036a3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036a43  nop
0x180036a44  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180036a48  call    cs:__imp_RtlFreeUnicodeString
0x180036a4e  nop
0x180036a4f  mov     eax, edi
0x180036a51  jmp     loc_180036B85
0x180036a56  lea     rax, [rbp+hMem]
0x180036a5a  mov     qword ptr [rsp+68h+var_48], rax; int
0x180036a5f  lea     r9, [rbp+arg_0]
0x180036a63  mov     r8, rbx
0x180036a66  lea     rdx, [rbp+UnicodeString]
0x180036a6a  xor     ecx, ecx
0x180036a6c  call    SetupBuffer
0x180036a71  mov     ebx, eax
0x180036a73  test    eax, eax
0x180036a75  jns     short loc_180036AB9
0x180036a77  mov     rcx, [rbp+20h]; this
0x180036a7b  mov     r9d, eax; char *
0x180036a7e  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\wldp\\dll\\endpoi"...
0x180036a85  mov     edx, 0ECh; void *
0x180036a8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036a8f  nop
0x180036a90  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180036a94  call    cs:__imp_RtlFreeUnicodeString
0x180036a9a  nop
0x180036a9b  mov     rcx, [rbp+hMem]; hMem
0x180036a9f  mov     [rbp+hMem], 0
0x180036aa7  test    rcx, rcx
0x180036aaa  jz      short loc_180036AB2
0x180036aac  call    cs:__imp_LocalFree
0x180036ab2  mov     eax, ebx
0x180036ab4  jmp     loc_180036B8D
0x180036ab9  lea     rax, [rbp+var_38]
0x180036abd  mov     [rsp+68h+var_40], rax
0x180036ac2  mov     [rsp+68h+var_48], 8; int
0x180036aca  lea     r9, [rbp+var_28]
0x180036ace  mov     r8d, [rbp+arg_0]
0x180036ad2  mov     rbx, [rbp+hMem]
0x180036ad6  mov     rdx, rbx
0x180036ad9  mov     ecx, 100h
0x180036ade  call    cs:__imp_NtQuerySystemInformationEx
0x180036ae4  mov     rcx, [rbp+20h]; this
0x180036ae8  test    eax, eax
0x180036aea  jns     short loc_180036B27
0x180036aec  mov     r9d, eax; char *
0x180036aef  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\wldp\\dll\\endpoi"...
0x180036af6  mov     edx, 0F3h; void *
0x180036afb  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180036b00  mov     edi, eax
0x180036b02  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180036b06  call    cs:__imp_RtlFreeUnicodeString
0x180036b0c  nop
0x180036b0d  mov     [rbp+hMem], 0
0x180036b15  test    rbx, rbx
0x180036b18  jz      short loc_180036B23
0x180036b1a  mov     rcx, rbx; hMem
0x180036b1d  call    cs:__imp_LocalFree
0x180036b23  mov     eax, edi
0x180036b25  jmp     short loc_180036B8D
0x180036b27  cmp     [rbp+var_38], 8
0x180036b2b  setnz   al
0x180036b2e  test    al, al
0x180036b30  jz      short loc_180036B49
0x180036b32  mov     r9d, 8000FFFFh; char *
0x180036b38  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\wldp\\dll\\endpoi"...
0x180036b3f  mov     edx, 0F5h; void *
0x180036b44  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180036b49  mov     rax, [rbp+var_28]
0x180036b4d  mov     [rsi], rax
0x180036b50  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180036b54  call    cs:__imp_RtlFreeUnicodeString
0x180036b5a  nop
0x180036b5b  mov     [rbp+hMem], 0
0x180036b63  test    rbx, rbx
0x180036b66  jz      short loc_180036B71
0x180036b68  mov     rcx, rbx; hMem
0x180036b6b  call    cs:__imp_LocalFree
0x180036b71  xor     eax, eax
0x180036b73  jmp     short loc_180036B8D
0x180036b75  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180036b79  call    cs:__imp_RtlFreeUnicodeString
0x180036b7f  nop
0x180036b80  mov     eax, 80070057h
0x180036b85  mov     [rbp+hMem], 0
0x180036b8d  add     rsp, 68h
0x180036b91  pop     rdi
0x180036b92  pop     rsi
0x180036b93  pop     rbx
0x180036b94  pop     rbp
0x180036b95  retn
```
