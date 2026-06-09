# TraceCloseClientConsoleA(x,x)

- ea: `0x10006f22`
- end: `0x10006fa6`
- name: `_TraceCloseClientConsoleA@8`
- size: `132`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x100023a6`
- `0x100027e0`
- `0x10007af9`

## callees

- `0x10006f22`
- `0x10009eb2`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10006f40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10006f81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10006f40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10006f81`
- `api-ms-win-core-console-l1-2-0!FreeConsole` at `0x10006f8d`
- `api-ms-win-core-console-l1-2-0!FreeConsole` at `0x10006f8d`

## pseudocode

```c
int __fastcall TraceCloseClientConsoleA(int a1, int a2)
{
  int v4; // eax
  int v5; // eax
  void *v6; // eax

  if ( (*(_BYTE *)(a1 + 32) & 4) != 0 )
  {
    v4 = *(_DWORD *)(a2 + 236);
    if ( v4 && v4 != -1 )
      CloseHandle(*(HANDLE *)(a2 + 236));
    *(_DWORD *)(a2 + 236) = 0;
    if ( *(_DWORD *)(a1 + 40) == *(_DWORD *)(a2 + 36) )
      TraceUpdateConsoleOwner(a1, 1);
    v5 = *(_DWORD *)(a1 + 40);
    if ( v5 == 60 || v5 == *(_DWORD *)(a2 + 36) )
    {
      v6 = *(void **)(a1 + 48);
      *(_DWORD *)(a1 + 40) = 60;
      if ( v6 && v6 != (void *)-1 )
        CloseHandle(v6);
      if ( *(_DWORD *)(a1 + 44) == 1 )
      {
        FreeConsole();
        *(_DWORD *)(a1 + 44) = 0;
      }
      *(_DWORD *)(a1 + 48) = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x10006f22  mov     edi, edi
0x10006f24  push    esi
0x10006f25  mov     esi, ecx
0x10006f27  push    edi
0x10006f28  mov     edi, edx
0x10006f2a  test    byte ptr [esi+20h], 4
0x10006f2e  jz      short loc_10006FA1
0x10006f30  mov     eax, [edi+0ECh]
0x10006f36  test    eax, eax
0x10006f38  jz      short loc_10006F46
0x10006f3a  cmp     eax, 0FFFFFFFFh
0x10006f3d  jz      short loc_10006F46
0x10006f3f  push    eax; hObject
0x10006f40  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10006f46  mov     dword ptr [edi+0ECh], 0
0x10006f50  mov     eax, [esi+28h]
0x10006f53  cmp     eax, [edi+24h]
0x10006f56  jnz     short loc_10006F62
0x10006f58  xor     edx, edx
0x10006f5a  mov     ecx, esi
0x10006f5c  inc     edx
0x10006f5d  call    _TraceUpdateConsoleOwner@8; TraceUpdateConsoleOwner(x,x)
0x10006f62  mov     eax, [esi+28h]
0x10006f65  push    3Ch ; '<'
0x10006f67  pop     ecx
0x10006f68  cmp     eax, ecx
0x10006f6a  jz      short loc_10006F71
0x10006f6c  cmp     eax, [edi+24h]
0x10006f6f  jnz     short loc_10006FA1
0x10006f71  mov     eax, [esi+30h]
0x10006f74  mov     [esi+28h], ecx
0x10006f77  test    eax, eax
0x10006f79  jz      short loc_10006F87
0x10006f7b  cmp     eax, 0FFFFFFFFh
0x10006f7e  jz      short loc_10006F87
0x10006f80  push    eax; hObject
0x10006f81  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10006f87  cmp     dword ptr [esi+2Ch], 1
0x10006f8b  jnz     short loc_10006F9A
0x10006f8d  call    ds:__imp__FreeConsole@0; FreeConsole()
0x10006f93  mov     dword ptr [esi+2Ch], 0
0x10006f9a  mov     dword ptr [esi+30h], 0
0x10006fa1  pop     edi
0x10006fa2  xor     eax, eax
0x10006fa4  pop     esi
0x10006fa5  retn
```
