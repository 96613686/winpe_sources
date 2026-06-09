# SetProfilesLocation

- ea: `0x14003afc0`
- end: `0x14003b0cc`
- name: `SetProfilesLocation`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400877f0`

## callees

- `0x1400057f4`
- `0x14003afc0`
- `0x140053720`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b02a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b02a`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14003b003`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14003b072`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14003b09b`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14003b0ad`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14003b003`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14003b072`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14003b09b`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14003b0ad`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x14003afed`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x14003b05c`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x14003b085`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x14003afed`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x14003b05c`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x14003b085`

## string_xrefs

- `0x14003b094`: `ProgramData`

## pseudocode

```c
int SetProfilesLocation()
{
  DWORD LastError; // eax
  int result; // eax
  WCHAR Value[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( (int)GetBasicProfileFolderPath(5, 0, Value, 260) < 0 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_dee1fec175ed3bc1a62ebb36f32fb4e0_Traceguids, LastError);
    }
  }
  else
  {
    SetEnvironmentVariableW(L"USERPROFILE", Value);
  }
  if ( (int)GetBasicProfileFolderPath(3, 0, Value, 260) >= 0 )
    SetEnvironmentVariableW(L"PUBLIC", Value);
  result = GetBasicProfileFolderPath(4, 0, Value, 260);
  if ( result >= 0 )
  {
    SetEnvironmentVariableW(L"ProgramData", Value);
    return SetEnvironmentVariableW(L"ALLUSERSPROFILE", Value);
  }
  return result;
}

```

## disassembly

```asm
0x14003afc0  push    rbx
0x14003afc2  sub     rsp, 240h
0x14003afc9  mov     rax, cs:__security_cookie
0x14003afd0  xor     rax, rsp
0x14003afd3  mov     [rsp+248h+var_18], rax
0x14003afdb  xor     edx, edx
0x14003afdd  lea     r8, [rsp+248h+Value]
0x14003afe2  mov     ebx, 104h
0x14003afe7  mov     r9d, ebx
0x14003afea  lea     ecx, [rdx+5]
0x14003afed  call    cs:__imp_GetBasicProfileFolderPath
0x14003aff3  test    eax, eax
0x14003aff5  js      short loc_14003B00B
0x14003aff7  lea     rdx, [rsp+248h+Value]; lpValue
0x14003affc  lea     rcx, aUserprofile; "USERPROFILE"
0x14003b003  call    cs:__imp_SetEnvironmentVariableW
0x14003b009  jmp     short loc_14003B04F
0x14003b00b  mov     rax, cs:WPP_GLOBAL_Control
0x14003b012  lea     rcx, WPP_GLOBAL_Control
0x14003b019  cmp     rax, rcx
0x14003b01c  jz      short loc_14003B04F
0x14003b01e  test    byte ptr [rax+1Ch], 1
0x14003b022  jz      short loc_14003B04F
0x14003b024  cmp     byte ptr [rax+19h], 2
0x14003b028  jb      short loc_14003B04F
0x14003b02a  call    cs:__imp_GetLastError
0x14003b030  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b037  lea     r8, WPP_dee1fec175ed3bc1a62ebb36f32fb4e0_Traceguids
0x14003b03e  mov     edx, 0Ah
0x14003b043  mov     r9d, eax
0x14003b046  mov     rcx, [rcx+10h]
0x14003b04a  call    WPP_SF_d
0x14003b04f  xor     edx, edx
0x14003b051  lea     r8, [rsp+248h+Value]
0x14003b056  mov     r9, rbx
0x14003b059  lea     ecx, [rdx+3]
0x14003b05c  call    cs:__imp_GetBasicProfileFolderPath
0x14003b062  test    eax, eax
0x14003b064  js      short loc_14003B078
0x14003b066  lea     rdx, [rsp+248h+Value]; lpValue
0x14003b06b  lea     rcx, aPublic; "PUBLIC"
0x14003b072  call    cs:__imp_SetEnvironmentVariableW
0x14003b078  xor     edx, edx
0x14003b07a  lea     r8, [rsp+248h+Value]
0x14003b07f  mov     r9, rbx
0x14003b082  lea     ecx, [rdx+4]
0x14003b085  call    cs:__imp_GetBasicProfileFolderPath
0x14003b08b  test    eax, eax
0x14003b08d  js      short loc_14003B0B3
0x14003b08f  lea     rdx, [rsp+248h+Value]; lpValue
0x14003b094  lea     rcx, aProgramdata; "ProgramData"
0x14003b09b  call    cs:__imp_SetEnvironmentVariableW
0x14003b0a1  lea     rdx, [rsp+248h+Value]; lpValue
0x14003b0a6  lea     rcx, aAllusersprofil; "ALLUSERSPROFILE"
0x14003b0ad  call    cs:__imp_SetEnvironmentVariableW
0x14003b0b3  mov     rcx, [rsp+248h+var_18]
0x14003b0bb  xor     rcx, rsp; StackCookie
0x14003b0be  call    __security_check_cookie
0x14003b0c3  add     rsp, 240h
0x14003b0ca  pop     rbx
0x14003b0cb  retn
```
