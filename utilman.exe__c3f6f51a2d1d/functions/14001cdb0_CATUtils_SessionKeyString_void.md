# CATUtils::SessionKeyString(void)

- ea: `0x14001cdb0`
- end: `0x14001ce57`
- name: `?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ`
- size: `167`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140015210`
- `0x140015c74`
- `0x140016e8c`
- `0x14001bf80`
- `0x14001c778`

## callees

- `0x140002480`
- `0x140002ed2`
- `0x140013b44`
- `0x140014058`
- `0x14001cdb0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x14001cdde`
- `KERNEL32!GetCurrentProcessId` at `0x14001cdde`
- `KERNEL32!ProcessIdToSessionId` at `0x14001cdf1`
- `KERNEL32!ProcessIdToSessionId` at `0x14001cdf1`

## string_xrefs

- `0x14001cdcb`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\Session`

## pseudocode

```c
__int64 __fastcall CATUtils::SessionKeyString(__int64 a1)
{
  DWORD CurrentProcessId; // eax
  __int64 v3; // r8
  DWORD pSessionId; // [rsp+20h] [rbp-38h] BYREF
  wchar_t Buffer[12]; // [rsp+28h] [rbp-30h] BYREF

  pSessionId = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    a1,
    L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\Session");
  CurrentProcessId = GetCurrentProcessId();
  if ( ProcessIdToSessionId(CurrentProcessId, &pSessionId) && !o__ltow_s_0(pSessionId, Buffer, 0xCu, 10) )
  {
    v3 = -1;
    do
      ++v3;
    while ( Buffer[v3] );
    ATL::CSimpleStringT<unsigned short,0>::Append(a1, Buffer, v3);
  }
  return a1;
}

```

## disassembly

```asm
0x14001cdb0  mov     [rsp+arg_8], rbx
0x14001cdb5  push    rdi
0x14001cdb6  sub     rsp, 50h
0x14001cdba  mov     rax, cs:__security_cookie
0x14001cdc1  xor     rax, rsp
0x14001cdc4  mov     [rsp+58h+var_18], rax
0x14001cdc9  xor     edi, edi
0x14001cdcb  lea     rdx, aSoftwareMicros_15; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001cdd2  mov     [rsp+58h+pSessionId], edi
0x14001cdd6  mov     rbx, rcx
0x14001cdd9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001cdde  call    cs:__imp_GetCurrentProcessId
0x14001cde5  nop     dword ptr [rax+rax+00h]
0x14001cdea  mov     ecx, eax; dwProcessId
0x14001cdec  lea     rdx, [rsp+58h+pSessionId]; pSessionId
0x14001cdf1  call    cs:__imp_ProcessIdToSessionId
0x14001cdf8  nop     dword ptr [rax+rax+00h]
0x14001cdfd  test    eax, eax
0x14001cdff  jz      short loc_14001CE3B
0x14001ce01  mov     ecx, [rsp+58h+pSessionId]; Value
0x14001ce05  lea     r9d, [rdi+0Ah]; Radix
0x14001ce09  lea     r8d, [rdi+0Ch]; BufferCount
0x14001ce0d  lea     rdx, [rsp+58h+Buffer]; Buffer
0x14001ce12  call    _o__ltow_s_0
0x14001ce17  test    eax, eax
0x14001ce19  jnz     short loc_14001CE3B
0x14001ce1b  lea     rax, [rsp+58h+Buffer]
0x14001ce20  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001ce24  inc     r8
0x14001ce27  cmp     [rax+r8*2], di
0x14001ce2c  jnz     short loc_14001CE24
0x14001ce2e  lea     rdx, [rsp+58h+Buffer]
0x14001ce33  mov     rcx, rbx
0x14001ce36  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14001ce3b  mov     rax, rbx
0x14001ce3e  mov     rcx, [rsp+58h+var_18]
0x14001ce43  xor     rcx, rsp; StackCookie
0x14001ce46  call    __security_check_cookie
0x14001ce4b  mov     rbx, [rsp+58h+arg_8]
0x14001ce50  add     rsp, 50h
0x14001ce54  pop     rdi
0x14001ce55  retn
```
