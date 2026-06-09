# std::variant<windiag::win_handle<void *,windiag::close_handle,0>,windiag::win_handle<void *,windiag::close_handle,-1>,windiag::win_handle<HINSTANCE__ *,windiag::close_dll,0>,windiag::win_handle<SC_HANDLE__ *,windiag::close_scm,0>,windiag::win_handle<void *,windiag::close_hlocal,0>,windiag::win_handle<HKEY__ *,windiag::close_hkey,0>>::variant<windiag::win_handle<void *,windiag::close_handle,0>,windiag::win_handle<void *,windiag::close_handle,-1>,windiag::win_handle<HINSTANCE__ *,windiag::close_dll,0>,windiag::win_handle<SC_HANDLE__ *,windiag::close_scm,0>,windiag::win_handle<void *,windiag::close_hlocal,0>,windiag::win_handle<HKEY__ *,windiag::close_hkey,0>>(std::variant<windiag::win_handle<void *,windiag::close_handle,0>,windiag::win_handle<void *,windiag::close_handle,-1>,windiag::win_handle<HINSTANCE__ *,windiag::close_dll,0>,windiag::win_handle<SC_HANDLE__ *,windiag::close_scm,0>,windiag::win_handle<void *,windiag::close_hlocal,0>,windiag::win_handle<HKEY__ *,windiag::close_hkey,0>> &&)

- ea: `0x1800796d8`
- end: `0x18007980c`
- name: `??0?$variant@U?$win_handle@PEAXUclose_handle@windiag@@$0A@@windiag@@U?$win_handle@PEAXUclose_handle@windiag@@$0?0@2@U?$win_handle@PEAUHINSTANCE__@@Uclose_dll@windiag@@$0A@@2@U?$win_handle@PEAUSC_HANDLE__@@Uclose_scm@windiag@@$0A@@2@U?$win_handle@PEAXUclose_hlocal@windiag@@$0A@@2@U?$win_handle@PEAUHKEY__@@Uclose_hkey@windiag@@$0A@@2@@std@@QEAA@$$QEAV01@@Z`
- size: `308`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180079684`
- `0x18007a220`
- `0x18007a9b0`

## callees

- `0x1800796d8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800797a4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800797a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800797c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800797ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800797c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800797ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079757`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079757`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007977f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007977f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007973d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007973d`

## pseudocode

```c
__int64 __fastcall std::variant<windiag::win_handle<void *,windiag::close_handle,0>,windiag::win_handle<void *,windiag::close_handle,-1>,windiag::win_handle<HINSTANCE__ *,windiag::close_dll,0>,windiag::win_handle<SC_HANDLE__ *,windiag::close_scm,0>,windiag::win_handle<void *,windiag::close_hlocal,0>,windiag::win_handle<HKEY__ *,windiag::close_hkey,0>>::variant<windiag::win_handle<void *,windiag::close_handle,0>,windiag::win_handle<void *,windiag::close_handle,-1>,windiag::win_handle<HINSTANCE__ *,windiag::close_dll,0>,windiag::win_handle<SC_HANDLE__ *,windiag::close_scm,0>,windiag::win_handle<void *,windiag::close_hlocal,0>,windiag::win_handle<HKEY__ *,windiag::close_hkey,0>>(
        __int64 a1,
        __int64 *a2)
{
  __int64 v3; // rax
  __int64 v4; // rsi
  HKEY v5; // rcx
  __int64 v6; // rsi
  SC_HANDLE v7; // rcx
  __int64 v8; // rsi
  HMODULE v9; // rcx
  __int64 v10; // rdi
  void *v11; // rcx
  __int64 v12; // rsi
  HMODULE v13; // rcx

  *(_BYTE *)(a1 + 8) = -1;
  if ( *((char *)a2 + 8) != -1 )
  {
    if ( *((_BYTE *)a2 + 8) )
    {
      if ( *((_BYTE *)a2 + 8) == 1 )
      {
        *(_QWORD *)a1 = -1;
        v10 = *a2;
        *a2 = -1;
        v11 = *(void **)a1;
        if ( v11 != (void *)-1LL )
        {
          *(_QWORD *)a1 = -1;
          CloseHandle(v11);
        }
        *(_QWORD *)a1 = v10;
        *(_BYTE *)(a1 + 8) = 1;
      }
      else if ( *((_BYTE *)a2 + 8) == 2 )
      {
        *(_QWORD *)a1 = 0;
        v8 = *a2;
        *a2 = 0;
        v9 = *(HMODULE *)a1;
        if ( v9 )
        {
          *(_QWORD *)a1 = 0;
          FreeLibrary(v9);
        }
        *(_QWORD *)a1 = v8;
        *(_BYTE *)(a1 + 8) = 2;
      }
      else
      {
        v3 = *((char *)a2 + 8) - 3LL;
        if ( *((_BYTE *)a2 + 8) == 3 )
        {
          *(_QWORD *)a1 = 0;
          v6 = *a2;
          *a2 = 0;
          v7 = *(SC_HANDLE *)a1;
          if ( v7 )
          {
            *(_QWORD *)a1 = 0;
            CloseServiceHandle(v7);
          }
          *(_QWORD *)a1 = v6;
          *(_BYTE *)(a1 + 8) = 3;
        }
        else
        {
          *(_QWORD *)a1 = 0;
          v4 = *a2;
          *a2 = 0;
          v5 = *(HKEY *)a1;
          if ( v3 == 1 )
          {
            if ( v5 )
            {
              *(_QWORD *)a1 = 0;
              LocalFree(v5);
            }
            *(_QWORD *)a1 = v4;
            *(_BYTE *)(a1 + 8) = 4;
          }
          else
          {
            if ( v5 )
            {
              *(_QWORD *)a1 = 0;
              RegCloseKey(v5);
            }
            *(_QWORD *)a1 = v4;
            *(_BYTE *)(a1 + 8) = 5;
          }
        }
      }
    }
    else
    {
      *(_QWORD *)a1 = 0;
      v12 = *a2;
      *a2 = 0;
      v13 = *(HMODULE *)a1;
      if ( v13 )
      {
        *(_QWORD *)a1 = 0;
        CloseHandle(v13);
      }
      *(_QWORD *)a1 = v12;
      *(_BYTE *)(a1 + 8) = 0;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800796d8  mov     [rsp+arg_0], rbx
0x1800796dd  mov     [rsp+arg_8], rsi
0x1800796e2  push    rdi
0x1800796e3  sub     rsp, 20h
0x1800796e7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800796eb  mov     rbx, rcx
0x1800796ee  mov     [rcx+8], r8b
0x1800796f2  movsx   rax, byte ptr [rdx+8]
0x1800796f7  add     rax, 1
0x1800796fb  jz      loc_1800797F9
0x180079701  sub     rax, 1
0x180079705  jz      loc_1800797D6
0x18007970b  sub     rax, 1
0x18007970f  jz      loc_1800797B3
0x180079715  sub     rax, 1
0x180079719  jz      short loc_18007978E
0x18007971b  sub     rax, 1
0x18007971f  jz      short loc_180079769
0x180079721  xor     edi, edi
0x180079723  mov     [rcx], rdi
0x180079726  mov     rsi, [rdx]
0x180079729  mov     [rdx], rdi
0x18007972c  mov     rcx, [rcx]; hMem
0x18007972f  cmp     rax, 1
0x180079733  jz      short loc_18007974F
0x180079735  test    rcx, rcx
0x180079738  jz      short loc_180079743
0x18007973a  mov     [rbx], rdi
0x18007973d  call    cs:__imp_RegCloseKey
0x180079743  mov     [rbx], rsi
0x180079746  mov     byte ptr [rbx+8], 5
0x18007974a  jmp     loc_1800797F9
0x18007974f  test    rcx, rcx
0x180079752  jz      short loc_18007975D
0x180079754  mov     [rbx], rdi
0x180079757  call    cs:__imp_LocalFree
0x18007975d  mov     [rbx], rsi
0x180079760  mov     byte ptr [rbx+8], 4
0x180079764  jmp     loc_1800797F9
0x180079769  xor     edi, edi
0x18007976b  mov     [rcx], rdi
0x18007976e  mov     rsi, [rdx]
0x180079771  mov     [rdx], rdi
0x180079774  mov     rcx, [rcx]; hSCObject
0x180079777  test    rcx, rcx
0x18007977a  jz      short loc_180079785
0x18007977c  mov     [rbx], rdi
0x18007977f  call    cs:__imp_CloseServiceHandle
0x180079785  mov     [rbx], rsi
0x180079788  mov     byte ptr [rbx+8], 3
0x18007978c  jmp     short loc_1800797F9
0x18007978e  xor     edi, edi
0x180079790  mov     [rcx], rdi
0x180079793  mov     rsi, [rdx]
0x180079796  mov     [rdx], rdi
0x180079799  mov     rcx, [rcx]; hLibModule
0x18007979c  test    rcx, rcx
0x18007979f  jz      short loc_1800797AA
0x1800797a1  mov     [rbx], rdi
0x1800797a4  call    cs:__imp_FreeLibrary
0x1800797aa  mov     [rbx], rsi
0x1800797ad  mov     byte ptr [rbx+8], 2
0x1800797b1  jmp     short loc_1800797F9
0x1800797b3  mov     [rcx], r8
0x1800797b6  mov     rdi, [rdx]
0x1800797b9  mov     [rdx], r8
0x1800797bc  mov     rcx, [rcx]; hObject
0x1800797bf  cmp     rcx, r8
0x1800797c2  jz      short loc_1800797CD
0x1800797c4  mov     [rbx], r8
0x1800797c7  call    cs:__imp_CloseHandle
0x1800797cd  mov     [rbx], rdi
0x1800797d0  mov     byte ptr [rbx+8], 1
0x1800797d4  jmp     short loc_1800797F9
0x1800797d6  xor     edi, edi
0x1800797d8  mov     [rcx], rdi
0x1800797db  mov     rsi, [rdx]
0x1800797de  mov     [rdx], rdi
0x1800797e1  mov     rcx, [rcx]; hObject
0x1800797e4  test    rcx, rcx
0x1800797e7  jz      short loc_1800797F2
0x1800797e9  mov     [rbx], rdi
0x1800797ec  call    cs:__imp_CloseHandle
0x1800797f2  mov     [rbx], rsi
0x1800797f5  mov     [rbx+8], dil
0x1800797f9  mov     rsi, [rsp+28h+arg_8]
0x1800797fe  mov     rax, rbx
0x180079801  mov     rbx, [rsp+28h+arg_0]
0x180079806  add     rsp, 20h
0x18007980a  pop     rdi
0x18007980b  retn
```
