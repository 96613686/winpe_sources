# CWshEnvRegistry::Remove(ushort *)

- ea: `0x18000b8a0`
- end: `0x18000b953`
- name: `?Remove@CWshEnvRegistry@@UEAAJPEAG@Z`
- size: `179`
- prototype: `int(CWshEnvRegistry *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x180005d20`
- `0x18000b8a0`
- `0x18000b95c`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x18000b8c8`
- `ADVAPI32!RegDeleteValueW` at `0x18000b8c8`
- `USER32!SendMessageTimeoutA` at `0x18000b920`
- `USER32!SendMessageTimeoutA` at `0x18000b920`

## string_xrefs

- `0x18000b92d`: `WshEnvironment.Remove`

## pseudocode

```c
__int64 __fastcall CWshEnvRegistry::Remove(HKEY *this, unsigned __int16 *a2)
{
  const WCHAR *v2; // rdi
  LSTATUS v3; // eax
  signed int v4; // ebx
  ULONG_PTR dwResult; // [rsp+58h] [rbp+10h] BYREF

  v2 = &psz;
  if ( a2 )
    v2 = a2;
  if ( Global::g_fWindowsNT )
  {
    v3 = RegDeleteValueW(this[9], v2);
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
  }
  else
  {
    v4 = CWshEnvRegistry::RemoveA((CWshEnvRegistry *)this, v2);
  }
  if ( v4 < 0 )
  {
    Signal_Exception(&IID_IWshEnvironment, L"WshEnvironment.Remove", 0x100Cu, v2);
  }
  else
  {
    dwResult = 0;
    SendMessageTimeoutA(HWND_BROADCAST, 0x1Au, 0, (LPARAM)"Environment", 0, 0x3E8u, &dwResult);
    return 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000b8a0  mov     [rsp+arg_0], rbx
0x18000b8a5  push    rdi
0x18000b8a6  sub     rsp, 40h
0x18000b8aa  test    rdx, rdx
0x18000b8ad  lea     rdi, psz
0x18000b8b4  cmovnz  rdi, rdx
0x18000b8b8  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x18000b8bf  mov     rdx, rdi; unsigned __int16 *
0x18000b8c2  jz      short loc_18000B8DF
0x18000b8c4  mov     rcx, [rcx+48h]; hKey
0x18000b8c8  call    cs:__imp_RegDeleteValueW
0x18000b8ce  mov     ebx, eax
0x18000b8d0  test    eax, eax
0x18000b8d2  jle     short loc_18000B8E6
0x18000b8d4  movzx   ebx, ax
0x18000b8d7  or      ebx, 80070000h
0x18000b8dd  jmp     short loc_18000B8E6
0x18000b8df  call    ?RemoveA@CWshEnvRegistry@@AEAAJPEBG@Z; CWshEnvRegistry::RemoveA(ushort const *)
0x18000b8e4  mov     ebx, eax
0x18000b8e6  test    ebx, ebx
0x18000b8e8  js      short loc_18000B92A
0x18000b8ea  xor     r8d, r8d; wParam
0x18000b8ed  mov     [rsp+48h+dwResult], 0
0x18000b8f6  lea     rax, [rsp+48h+dwResult]
0x18000b8fb  mov     ecx, 0FFFFh; hWnd
0x18000b900  mov     [rsp+48h+lpdwResult], rax; lpdwResult
0x18000b905  lea     r9, aEnvironment; "Environment"
0x18000b90c  mov     [rsp+48h+uTimeout], 3E8h; uTimeout
0x18000b914  lea     edx, [r8+1Ah]; Msg
0x18000b918  mov     [rsp+48h+fuFlags], 0; fuFlags
0x18000b920  call    cs:__imp_SendMessageTimeoutA
0x18000b926  xor     ebx, ebx
0x18000b928  jmp     short loc_18000B946
0x18000b92a  mov     r9, rdi
0x18000b92d  lea     rdx, aWshenvironment; "WshEnvironment.Remove"
0x18000b934  mov     r8d, 100Ch; unsigned int
0x18000b93a  lea     rcx, IID_IWshEnvironment; struct _GUID *
0x18000b941  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x18000b946  mov     eax, ebx
0x18000b948  mov     rbx, [rsp+48h+arg_0]
0x18000b94d  add     rsp, 40h
0x18000b951  pop     rdi
0x18000b952  retn
```
