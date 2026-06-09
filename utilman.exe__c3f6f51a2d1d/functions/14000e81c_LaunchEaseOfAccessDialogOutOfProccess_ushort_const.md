# LaunchEaseOfAccessDialogOutOfProccess(ushort const *)

- ea: `0x14000e81c`
- end: `0x14000e8a2`
- name: `?LaunchEaseOfAccessDialogOutOfProccess@@YAXPEBG@Z`
- size: `134`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000e2a0`

## callees

- `0x140002480`
- `0x14000e81c`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x14000e847`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14000e847`
- `SHELL32!ShellExecuteW` at `0x14000e87d`
- `SHELL32!ShellExecuteW` at `0x14000e87d`

## string_xrefs

- `0x14000e840`: `%SystemRoot%\system32\EaseOfAccessDialog.exe`

## pseudocode

```c
void __fastcall LaunchEaseOfAccessDialogOutOfProccess(const unsigned __int16 *a1)
{
  WCHAR Dst[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\system32\\EaseOfAccessDialog.exe", Dst, 0x104u) - 1 <= 0x102 )
    ShellExecuteW(0, 0, Dst, L"261", 0, 10);
}

```

## disassembly

```asm
0x14000e81c  sub     rsp, 258h
0x14000e823  mov     rax, cs:__security_cookie
0x14000e82a  xor     rax, rsp
0x14000e82d  mov     [rsp+258h+var_18], rax
0x14000e835  mov     r8d, 104h; nSize
0x14000e83b  lea     rdx, [rsp+258h+Dst]; lpDst
0x14000e840  lea     rcx, Src; "%SystemRoot%\\system32\\EaseOfAccessDia"...
0x14000e847  call    cs:__imp_ExpandEnvironmentStringsW
0x14000e84e  nop     dword ptr [rax+rax+00h]
0x14000e853  dec     eax
0x14000e855  cmp     eax, 102h
0x14000e85a  ja      short loc_14000E889
0x14000e85c  mov     [rsp+258h+nShowCmd], 0Ah; nShowCmd
0x14000e864  lea     r9, Parameters; "261"
0x14000e86b  lea     r8, [rsp+258h+Dst]; lpFile
0x14000e870  mov     [rsp+258h+lpDirectory], 0; lpDirectory
0x14000e879  xor     edx, edx; lpOperation
0x14000e87b  xor     ecx, ecx; hwnd
0x14000e87d  call    cs:__imp_ShellExecuteW
0x14000e884  nop     dword ptr [rax+rax+00h]
0x14000e889  mov     rcx, [rsp+258h+var_18]
0x14000e891  xor     rcx, rsp; StackCookie
0x14000e894  call    __security_check_cookie
0x14000e899  add     rsp, 258h
0x14000e8a0  retn
```
