# Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>::GetKeyState(Windows::System::VirtualKey,Windows::UI::Core::CoreVirtualKeyStates *)

- ea: `0x180029810`
- end: `0x1800298d9`
- name: `?GetKeyState@?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreComponentInputSource@@3QBGB@Core@UI@Windows@@UEAAJW4VirtualKey@System@4@PEAW4CoreVirtualKeyStates@234@@Z`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18006e900`

## callees

- `0x180029810`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002984b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002984b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180029834`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800298a7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180029834`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800298a7`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyState` at `0x1800298bf`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyState` at `0x1800298bf`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::CCoreInput<&unsigned short const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>::GetKeyState(
        __int64 a1,
        unsigned int a2,
        _DWORD *a3)
{
  __int64 v3; // rdi
  int v8; // edi
  __int64 v9; // rcx
  unsigned int v10; // ebx
  SHORT KeyState; // ax

  v3 = *(_QWORD *)(a1 + 128);
  if ( v3 && (v8 = *(_DWORD *)(v3 + 120), GetCurrentThreadId() == v8) )
  {
    if ( *(_DWORD *)(a1 + 1208) == 1 )
    {
      if ( a3 )
      {
        *a3 = 0;
        v9 = *(_QWORD *)(a1 + 120);
        if ( v9 )
        {
          return (*(unsigned int (__fastcall **)(__int64, _QWORD, _DWORD *))(*(_QWORD *)v9 + 104LL))(v9, a2, a3);
        }
        else
        {
          v10 = 0;
          KeyState = GetKeyState(a2);
          if ( (KeyState & 1) != 0 )
            *a3 = 2;
          if ( KeyState < 0 )
            *a3 |= 1u;
        }
        return v10;
      }
      else
      {
        return 2147942487LL;
      }
    }
    else
    {
      RoOriginateError(2147549482LL, 0);
      return 2147549482LL;
    }
  }
  else
  {
    RoOriginateError(2147549454LL, 0);
    return 2147549454LL;
  }
}

```

## disassembly

```asm
0x180029810  push    rbx
0x180029812  push    rbp
0x180029813  push    rsi
0x180029814  push    rdi
0x180029815  sub     rsp, 28h
0x180029819  mov     rdi, [rcx+80h]
0x180029820  mov     rsi, r8
0x180029823  mov     ebp, edx
0x180029825  mov     rbx, rcx
0x180029828  test    rdi, rdi
0x18002982b  jnz     short loc_180029848
0x18002982d  xor     edx, edx
0x18002982f  mov     ecx, 8001010Eh
0x180029834  call    cs:__imp_RoOriginateError
0x18002983a  mov     eax, 8001010Eh
0x18002983f  add     rsp, 28h
0x180029843  pop     rdi
0x180029844  pop     rsi
0x180029845  pop     rbp
0x180029846  pop     rbx
0x180029847  retn
0x180029848  mov     edi, [rdi+78h]
0x18002984b  call    cs:__imp_GetCurrentThreadId
0x180029851  cmp     eax, edi
0x180029853  jnz     short loc_18002982D
0x180029855  cmp     dword ptr [rbx+4B8h], 1
0x18002985c  jnz     short loc_1800298A0
0x18002985e  test    rsi, rsi
0x180029861  jz      short loc_180029890
0x180029863  mov     dword ptr [rsi], 0
0x180029869  mov     rcx, [rbx+78h]
0x18002986d  test    rcx, rcx
0x180029870  jz      short loc_1800298BB
0x180029872  mov     rax, [rcx]
0x180029875  mov     r8, rsi
0x180029878  mov     edx, ebp
0x18002987a  mov     rax, [rax+68h]
0x18002987e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029883  mov     ebx, eax
0x180029885  mov     eax, ebx
0x180029887  add     rsp, 28h
0x18002988b  pop     rdi
0x18002988c  pop     rsi
0x18002988d  pop     rbp
0x18002988e  pop     rbx
0x18002988f  retn
0x180029890  mov     ebx, 80070057h
0x180029895  mov     eax, ebx
0x180029897  add     rsp, 28h
0x18002989b  pop     rdi
0x18002989c  pop     rsi
0x18002989d  pop     rbp
0x18002989e  pop     rbx
0x18002989f  retn
0x1800298a0  xor     edx, edx
0x1800298a2  mov     ecx, 8001012Ah
0x1800298a7  call    cs:__imp_RoOriginateError
0x1800298ad  mov     eax, 8001012Ah
0x1800298b2  add     rsp, 28h
0x1800298b6  pop     rdi
0x1800298b7  pop     rsi
0x1800298b8  pop     rbp
0x1800298b9  pop     rbx
0x1800298ba  retn
0x1800298bb  mov     ecx, ebp; nVirtKey
0x1800298bd  xor     ebx, ebx
0x1800298bf  call    cs:__imp_GetKeyState
0x1800298c5  test    al, 1
0x1800298c7  jz      short loc_1800298CF
0x1800298c9  mov     dword ptr [rsi], 2
0x1800298cf  test    ax, ax
0x1800298d2  jns     short loc_180029885
0x1800298d4  or      dword ptr [rsi], 1
0x1800298d7  jmp     short loc_180029885
```
