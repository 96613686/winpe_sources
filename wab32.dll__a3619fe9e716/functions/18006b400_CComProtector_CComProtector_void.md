# CComProtector::CComProtector(void)

- ea: `0x18006b400`
- end: `0x18006b4c2`
- name: `??0CComProtector@@QEAA@XZ`
- size: `194`
- prototype: `CComProtector *__fastcall(CComProtector *__hidden this)`
- caller_count: `11`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014da0`
- `0x180024a40`
- `0x18002e8a0`
- `0x18002f1c0`
- `0x18002f240`
- `0x18002ff20`
- `0x180038310`
- `0x1800389a0`
- `0x18003fec0`
- `0x18006b4c8`
- `0x180075960`

## callees

- `0x180064e84`
- `0x18006b400`
- `0x180091eaa`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18006b42c`
- `KERNEL32!GetCurrentThreadId` at `0x18006b42c`
- `ole32!CoUninitialize` at `0x18006b45e`
- `ole32!CoUninitialize` at `0x18006b45e`
- `ole32!CoInitializeEx` at `0x18006b453`
- `ole32!CoInitializeEx` at `0x18006b453`

## pseudocode

```c
CComProtector *__fastcall CComProtector::CComProtector(CComProtector *this)
{
  struct _tagPerThreadGlobalData *ThreadStoragePointer; // rbx
  int v3; // eax
  HRESULT v4; // eax

  *((_DWORD *)this + 65) = 0;
  memset_0(this, 0, 0x100u);
  ThreadStoragePointer = GetThreadStoragePointer();
  *((_DWORD *)this + 64) = GetCurrentThreadId();
  _InterlockedIncrement(&g_lObjectCount);
  if ( ThreadStoragePointer )
  {
    v3 = *((_DWORD *)ThreadStoragePointer + 627);
    if ( v3 )
    {
      if ( v3 != 1 )
        return this;
    }
    else
    {
      v4 = CoInitializeEx(0, 2u);
      if ( v4 == 1 )
      {
        CoUninitialize();
LABEL_6:
        *((_DWORD *)ThreadStoragePointer + 627) = 2;
        return this;
      }
      if ( v4 == -2147417850 )
        goto LABEL_6;
      if ( v4 < 0 )
      {
        *((_DWORD *)ThreadStoragePointer + 627) = 2;
        *((_DWORD *)ThreadStoragePointer + 626) = 0;
        *((_DWORD *)this + 65) = -2147467259;
        return this;
      }
      *((_DWORD *)ThreadStoragePointer + 627) = 1;
    }
    ++*((_DWORD *)ThreadStoragePointer + 626);
  }
  return this;
}

```

## disassembly

```asm
0x18006b400  mov     [rsp+arg_0], rbx
0x18006b405  push    rdi
0x18006b406  sub     rsp, 20h
0x18006b40a  xor     edx, edx; Val
0x18006b40c  mov     dword ptr [rcx+104h], 0
0x18006b416  mov     r8d, 100h; Size
0x18006b41c  mov     rdi, rcx
0x18006b41f  call    memset_0
0x18006b424  call    ?GetThreadStoragePointer@@YAPEAU_tagPerThreadGlobalData@@XZ; GetThreadStoragePointer(void)
0x18006b429  mov     rbx, rax
0x18006b42c  call    cs:__imp_GetCurrentThreadId
0x18006b432  mov     [rdi+100h], eax
0x18006b438  lock inc cs:?g_lObjectCount@@3JA; long g_lObjectCount
0x18006b43f  test    rbx, rbx
0x18006b442  jz      short loc_18006B4B4
0x18006b444  mov     eax, [rbx+9CCh]
0x18006b44a  test    eax, eax
0x18006b44c  jnz     short loc_18006B4A9
0x18006b44e  lea     edx, [rax+2]; dwCoInit
0x18006b451  xor     ecx, ecx; pvReserved
0x18006b453  call    cs:__imp_CoInitializeEx
0x18006b459  cmp     eax, 1
0x18006b45c  jnz     short loc_18006B466
0x18006b45e  call    cs:__imp_CoUninitialize
0x18006b464  jmp     short loc_18006B46D
0x18006b466  cmp     eax, 80010106h
0x18006b46b  jnz     short loc_18006B479
0x18006b46d  mov     dword ptr [rbx+9CCh], 2
0x18006b477  jmp     short loc_18006B4B4
0x18006b479  test    eax, eax
0x18006b47b  js      short loc_18006B489
0x18006b47d  mov     dword ptr [rbx+9CCh], 1
0x18006b487  jmp     short loc_18006B4AE
0x18006b489  mov     dword ptr [rbx+9CCh], 2
0x18006b493  mov     dword ptr [rbx+9C8h], 0
0x18006b49d  mov     dword ptr [rdi+104h], 80004005h
0x18006b4a7  jmp     short loc_18006B4B4
0x18006b4a9  cmp     eax, 1
0x18006b4ac  jnz     short loc_18006B4B4
0x18006b4ae  inc     dword ptr [rbx+9C8h]
0x18006b4b4  mov     rbx, [rsp+28h+arg_0]
0x18006b4b9  mov     rax, rdi
0x18006b4bc  add     rsp, 20h
0x18006b4c0  pop     rdi
0x18006b4c1  retn
```
