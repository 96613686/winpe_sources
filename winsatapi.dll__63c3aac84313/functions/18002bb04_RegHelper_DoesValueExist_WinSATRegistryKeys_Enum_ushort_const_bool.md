# RegHelper::DoesValueExist(WinSATRegistryKeys::Enum,ushort const *,bool &)

- ea: `0x18002bb04`
- end: `0x18002bbb1`
- name: `?DoesValueExist@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEA_N@Z`
- size: `173`
- prototype: `__int64 __fastcall(DWORD, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021294`

## callees

- `0x18000e234`
- `0x1800173a4`
- `0x18002bb04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bb7b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bb7b`

## string_xrefs

- `0x18002bb64`: `FirstIdleCompletionTimeDate`

## pseudocode

```c
__int64 __fastcall RegHelper::DoesValueExist(DWORD a1, __int64 a2, _BYTE *a3)
{
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  HKEY hKey[5]; // [rsp+30h] [rbp-28h] BYREF
  DWORD Type; // [rsp+60h] [rbp+8h] BYREF

  Type = a1;
  memset(hKey, 0, 24);
  v4 = ATL::CRegKey::Open(
         (ATL::CRegKey *)hKey,
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSATAPI",
         0x20019u);
  if ( !v4 )
  {
    Type = 0;
    v5 = RegQueryValueExW(hKey[0], L"FirstIdleCompletionTimeDate", 0, &Type, 0, 0);
    if ( v5 )
    {
      v4 = 2;
      if ( v5 == 2 )
        *a3 = 0;
      else
        v4 = v5;
    }
    else
    {
      *a3 = 1;
    }
  }
  ATL::CRegKey::Close(hKey);
  return v4;
}

```

## disassembly

```asm
0x18002bb04  mov     rax, rsp
0x18002bb07  mov     [rax+10h], rbx
0x18002bb0b  mov     [rax+8], ecx
0x18002bb0e  push    rdi
0x18002bb0f  sub     rsp, 50h
0x18002bb13  mov     rdi, r8
0x18002bb16  mov     qword ptr [rax-28h], 0
0x18002bb1e  lea     r8, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002bb25  mov     qword ptr [rax-20h], 0
0x18002bb2d  mov     r9d, 20019h; unsigned int
0x18002bb33  mov     qword ptr [rax-18h], 0
0x18002bb3b  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18002bb42  lea     rcx, [rax-28h]; this
0x18002bb46  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002bb4b  mov     ebx, eax
0x18002bb4d  test    eax, eax
0x18002bb4f  jnz     short loc_18002BB9A
0x18002bb51  mov     rcx, [rsp+58h+hKey]; hKey
0x18002bb56  lea     r9, [rsp+58h+Type]; lpType
0x18002bb5b  mov     [rsp+58h+lpcbData], 0; lpcbData
0x18002bb64  lea     rdx, ValueName; "FirstIdleCompletionTimeDate"
0x18002bb6b  xor     r8d, r8d; lpReserved
0x18002bb6e  mov     [rsp+58h+lpData], 0; lpData
0x18002bb77  mov     [rsp+58h+Type], eax
0x18002bb7b  call    cs:__imp_RegQueryValueExW
0x18002bb81  test    eax, eax
0x18002bb83  jnz     short loc_18002BB8A
0x18002bb85  mov     byte ptr [rdi], 1
0x18002bb88  jmp     short loc_18002BB9A
0x18002bb8a  mov     ebx, 2
0x18002bb8f  cmp     eax, ebx
0x18002bb91  jnz     short loc_18002BB98
0x18002bb93  mov     byte ptr [rdi], 0
0x18002bb96  jmp     short loc_18002BB9A
0x18002bb98  mov     ebx, eax
0x18002bb9a  lea     rcx, [rsp+58h+hKey]; this
0x18002bb9f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002bba4  mov     eax, ebx
0x18002bba6  mov     rbx, [rsp+58h+arg_8]
0x18002bbab  add     rsp, 50h
0x18002bbaf  pop     rdi
0x18002bbb0  retn
```
