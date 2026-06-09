# CDesktopManager::PostStartAnimations(void)

- ea: `0x18002e874`
- end: `0x18002e8f0`
- name: `?PostStartAnimations@CDesktopManager@@QEAAJXZ`
- size: `124`
- prototype: `__int64 __fastcall(CDesktopManager *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180007368`
- `0x18001a690`
- `0x18002dab4`
- `0x18002e700`
- `0x18009adf0`

## callees

- `0x18001f43c`
- `0x18002e874`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e8ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e8ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e883`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e883`
- `USER32!PostThreadMessageW` at `0x18002e89a`
- `USER32!PostThreadMessageW` at `0x18002e89a`

## pseudocode

```c
__int64 __fastcall CDesktopManager::PostStartAnimations(CDesktopManager *this)
{
  signed int v2; // ebx
  signed int LastError; // eax

  *((_BYTE *)this + 19) = 0;
  SetLastError(0);
  if ( PostThreadMessageW(*((_DWORD *)this + 282), 0x400u, 0, 0) )
  {
    return 0;
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 >= 0 )
      v2 = -2003304445;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v2, 0x666u, 0);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002e874  push    rbx
0x18002e876  sub     rsp, 30h
0x18002e87a  mov     rbx, rcx
0x18002e87d  mov     byte ptr [rcx+13h], 0
0x18002e881  xor     ecx, ecx; dwErrCode
0x18002e883  call    cs:__imp_SetLastError
0x18002e889  mov     ecx, [rbx+468h]; idThread
0x18002e88f  xor     r9d, r9d; lParam
0x18002e892  xor     r8d, r8d; wParam
0x18002e895  mov     edx, 400h; Msg
0x18002e89a  call    cs:__imp_PostThreadMessageW
0x18002e8a0  test    eax, eax
0x18002e8a2  jz      short loc_18002E8AE
0x18002e8a4  xor     ebx, ebx
0x18002e8a6  mov     eax, ebx
0x18002e8a8  add     rsp, 30h
0x18002e8ac  pop     rbx
0x18002e8ad  retn
0x18002e8ae  call    cs:__imp_GetLastError
0x18002e8b4  mov     ebx, eax
0x18002e8b6  test    eax, eax
0x18002e8b8  jle     short loc_18002E8C3
0x18002e8ba  movzx   ebx, ax
0x18002e8bd  or      ebx, 80070000h
0x18002e8c3  test    ebx, ebx
0x18002e8c5  mov     [rsp+38h+var_10], 0; void *
0x18002e8ce  mov     eax, 88980003h
0x18002e8d3  mov     [rsp+38h+var_18], 666h; unsigned int
0x18002e8db  cmovns  ebx, eax
0x18002e8de  xor     edx, edx; int *
0x18002e8e0  mov     r9d, ebx; int
0x18002e8e3  xor     r8d, r8d; unsigned int
0x18002e8e6  lea     ecx, [rdx+14h]; unsigned int
0x18002e8e9  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18002e8ee  jmp     short loc_18002E8A6
```
