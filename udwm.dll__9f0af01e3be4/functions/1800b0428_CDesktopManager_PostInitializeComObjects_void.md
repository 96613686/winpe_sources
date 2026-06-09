# CDesktopManager::PostInitializeComObjects(void)

- ea: `0x1800b0428`
- end: `0x1800b04a0`
- name: `?PostInitializeComObjects@CDesktopManager@@QEAAJXZ`
- size: `120`
- prototype: `__int64 __fastcall(CDesktopManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800b1260`

## callees

- `0x18001f43c`
- `0x1800b0428`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0454`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b0433`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b0433`
- `USER32!PostThreadMessageW` at `0x1800b044a`
- `USER32!PostThreadMessageW` at `0x1800b044a`

## pseudocode

```c
__int64 __fastcall CDesktopManager::PostInitializeComObjects(CDesktopManager *this)
{
  signed int LastError; // eax
  signed int v3; // ebx

  SetLastError(0);
  if ( PostThreadMessageW(*((_DWORD *)this + 282), 0x409u, 0, 0) )
  {
    return 0;
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
      v3 = -2003304445;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v3, 0x672u, 0);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800b0428  push    rbx
0x1800b042a  sub     rsp, 30h
0x1800b042e  mov     rbx, rcx
0x1800b0431  xor     ecx, ecx; dwErrCode
0x1800b0433  call    cs:__imp_SetLastError
0x1800b0439  mov     ecx, [rbx+468h]; idThread
0x1800b043f  xor     r9d, r9d; lParam
0x1800b0442  xor     r8d, r8d; wParam
0x1800b0445  mov     edx, 409h; Msg
0x1800b044a  call    cs:__imp_PostThreadMessageW
0x1800b0450  test    eax, eax
0x1800b0452  jnz     short loc_1800B0496
0x1800b0454  call    cs:__imp_GetLastError
0x1800b045a  mov     ebx, eax
0x1800b045c  test    eax, eax
0x1800b045e  jle     short loc_1800B0469
0x1800b0460  movzx   ebx, ax
0x1800b0463  or      ebx, 80070000h
0x1800b0469  test    ebx, ebx
0x1800b046b  mov     [rsp+38h+var_10], 0; void *
0x1800b0474  mov     eax, 88980003h
0x1800b0479  mov     [rsp+38h+var_18], 672h; unsigned int
0x1800b0481  cmovns  ebx, eax
0x1800b0484  xor     edx, edx; int *
0x1800b0486  mov     r9d, ebx; int
0x1800b0489  xor     r8d, r8d; unsigned int
0x1800b048c  lea     ecx, [rdx+14h]; unsigned int
0x1800b048f  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800b0494  jmp     short loc_1800B0498
0x1800b0496  xor     ebx, ebx
0x1800b0498  mov     eax, ebx
0x1800b049a  add     rsp, 30h
0x1800b049e  pop     rbx
0x1800b049f  retn
```
