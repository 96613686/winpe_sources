# ComTaskMgrBase::IsDebuggerBreakForTaskStartEnabled(ushort const *)

- ea: `0x140006550`
- end: `0x14000664c`
- name: `?IsDebuggerBreakForTaskStartEnabled@ComTaskMgrBase@@KAHPEBG@Z`
- size: `252`
- prototype: `_BOOL8 __fastcall(wchar_t *SubStr)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140009910`

## callees

- `0x140006550`
- `0x140007b4f`
- `0x140009330`
- `0x14000a2d0`

## import_xrefs

- `msvcrt!wcsstr` at `0x140006633`
- `msvcrt!wcsstr` at `0x140006633`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400065c0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400065c0`

## string_xrefs

- `0x140006592`: `EnableDebuggerBreakForTaskStart`

## pseudocode

```c
_BOOL8 __fastcall ComTaskMgrBase::IsDebuggerBreakForTaskStartEnabled(wchar_t *SubStr)
{
  unsigned int ValueW; // eax
  DWORD pcbData[4]; // [rsp+40h] [rbp-238h] BYREF
  wchar_t Str[264]; // [rsp+50h] [rbp-228h] BYREF

  memset_0(Str, 0, 0x20Au);
  pcbData[0] = 522;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule",
             L"EnableDebuggerBreakForTaskStart",
             0x22u,
             0,
             Str,
             pcbData);
  if ( ValueW )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_70d3f6ab2bd730cad06006a8dcaaa1a7_Traceguids, ValueW);
    return 0;
  }
  else
  {
    return !SubStr || !Str[0] || !*SubStr || wcsstr(Str, SubStr) != 0;
  }
}

```

## disassembly

```asm
0x140006550  push    rbx
0x140006552  sub     rsp, 270h
0x140006559  mov     rax, cs:__security_cookie
0x140006560  xor     rax, rsp
0x140006563  mov     [rsp+278h+var_18], rax
0x14000656b  mov     rbx, rcx
0x14000656e  xor     edx, edx; Val
0x140006570  lea     rcx, [rsp+278h+Str]; void *
0x140006575  mov     r8d, 20Ah; Size
0x14000657b  call    memset_0
0x140006580  lea     rax, [rsp+278h+var_238]
0x140006585  mov     [rsp+278h+var_238], 20Ah
0x14000658d  mov     [rsp+278h+pcbData], rax; pcbData
0x140006592  lea     r8, aEnabledebugger_0; "EnableDebuggerBreakForTaskStart"
0x140006599  lea     rax, [rsp+278h+Str]
0x14000659e  mov     r9d, 22h ; '"'; dwFlags
0x1400065a4  mov     [rsp+278h+pvData], rax; pvData
0x1400065a9  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400065b0  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1400065b7  mov     [rsp+278h+pdwType], 0; pdwType
0x1400065c0  call    cs:__imp_RegGetValueW
0x1400065c6  test    eax, eax
0x1400065c8  jz      short loc_140006618
0x1400065ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400065d1  lea     rdx, WPP_GLOBAL_Control
0x1400065d8  cmp     rcx, rdx
0x1400065db  jnz     short loc_1400065F8
0x1400065dd  xor     eax, eax
0x1400065df  mov     rcx, [rsp+278h+var_18]
0x1400065e7  xor     rcx, rsp; StackCookie
0x1400065ea  call    __security_check_cookie
0x1400065ef  add     rsp, 270h
0x1400065f6  pop     rbx
0x1400065f7  retn
0x1400065f8  test    byte ptr [rcx+1Ch], 1
0x1400065fc  jz      short loc_1400065DD
0x1400065fe  mov     rcx, [rcx+10h]
0x140006602  lea     r8, WPP_70d3f6ab2bd730cad06006a8dcaaa1a7_Traceguids
0x140006609  mov     edx, 0Eh
0x14000660e  mov     r9d, eax
0x140006611  call    WPP_SF_d
0x140006616  jmp     short loc_1400065DD
0x140006618  test    rbx, rbx
0x14000661b  jz      short loc_140006645
0x14000661d  cmp     [rsp+278h+Str], 0
0x140006623  jz      short loc_140006645
0x140006625  cmp     word ptr [rbx], 0
0x140006629  jz      short loc_140006645
0x14000662b  mov     rdx, rbx; SubStr
0x14000662e  lea     rcx, [rsp+278h+Str]; Str
0x140006633  call    cs:__imp_wcsstr
0x140006639  xor     ecx, ecx
0x14000663b  test    rax, rax
0x14000663e  setnz   cl
0x140006641  mov     eax, ecx
0x140006643  jmp     short loc_1400065DF
0x140006645  mov     eax, 1
0x14000664a  jmp     short loc_1400065DF
```
