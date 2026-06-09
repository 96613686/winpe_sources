# AppModule::Uninit(void)

- ea: `0x1400108dc`
- end: `0x140010a9a`
- name: `?Uninit@AppModule@@QEAAXXZ`
- size: `446`
- prototype: `void __fastcall(AppModule *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14000c488`

## callees

- `0x140001258`
- `0x14000f674`
- `0x1400108dc`
- `0x140013490`

## import_xrefs

- `ADVAPI32!RegDeleteKeyValueW` at `0x1400109ca`
- `ADVAPI32!RegDeleteKeyValueW` at `0x1400109ca`
- `ADVAPI32!EventUnregister` at `0x140010a6b`
- `ADVAPI32!EventUnregister` at `0x140010a6b`
- `KERNEL32!CloseHandle` at `0x140010a55`
- `KERNEL32!CloseHandle` at `0x140010a7e`
- `KERNEL32!CloseHandle` at `0x140010a55`
- `KERNEL32!CloseHandle` at `0x140010a7e`
- `KERNEL32!DeleteCriticalSection` at `0x14001095e`
- `KERNEL32!DeleteCriticalSection` at `0x14001095e`
- `KERNEL32!LocalFree` at `0x1400108f9`
- `KERNEL32!LocalFree` at `0x14001090c`
- `KERNEL32!LocalFree` at `0x14001091f`
- `KERNEL32!LocalFree` at `0x140010932`
- `KERNEL32!LocalFree` at `0x140010945`
- `KERNEL32!LocalFree` at `0x1400108f9`
- `KERNEL32!LocalFree` at `0x14001090c`
- `KERNEL32!LocalFree` at `0x14001091f`
- `KERNEL32!LocalFree` at `0x140010932`
- `KERNEL32!LocalFree` at `0x140010945`
- `KERNEL32!SetEvent` at `0x1400109d9`
- `KERNEL32!SetEvent` at `0x1400109d9`
- `KERNEL32!WaitForSingleObject` at `0x140010a09`
- `KERNEL32!WaitForSingleObject` at `0x140010a09`
- `OLEAUT32!__imp_SysFreeString` at `0x140010988`
- `OLEAUT32!__imp_SysFreeString` at `0x140010a1b`
- `OLEAUT32!__imp_SysFreeString` at `0x140010988`
- `OLEAUT32!__imp_SysFreeString` at `0x140010a1b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001096c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001096c`

## string_xrefs

- `0x1400109b5`: `WUSACommandLine`

## pseudocode

```c
void __fastcall AppModule::Uninit(AppModule *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  OLECHAR *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  OLECHAR *v11; // rcx
  char *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx

  if ( !*((_DWORD *)this + 26) )
  {
    v2 = (void *)*((_QWORD *)this + 5);
    if ( v2 )
    {
      LocalFree(v2);
      *((_QWORD *)this + 5) = 0;
    }
    v3 = (void *)*((_QWORD *)this + 6);
    if ( v3 )
    {
      LocalFree(v3);
      *((_QWORD *)this + 6) = 0;
    }
    v4 = (void *)*((_QWORD *)this + 7);
    if ( v4 )
    {
      LocalFree(v4);
      *((_QWORD *)this + 7) = 0;
    }
    v5 = (void *)*((_QWORD *)this + 8);
    if ( v5 )
    {
      LocalFree(v5);
      *((_QWORD *)this + 8) = 0;
    }
    v6 = (void *)*((_QWORD *)this + 9);
    if ( v6 )
    {
      LocalFree(v6);
      *((_QWORD *)this + 9) = 0;
    }
  }
  if ( *((_DWORD *)this + 74) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 256));
  if ( !*((_DWORD *)this + 59) )
  {
    CoUninitialize();
    *((_DWORD *)this + 59) = 1;
  }
  v7 = (OLECHAR *)*((_QWORD *)this + 19);
  if ( v7 )
  {
    SysFreeString(v7);
    *((_QWORD *)this + 19) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 25);
  if ( v8 )
  {
    operator delete(v8);
    *((_QWORD *)this + 25) = 0;
  }
  AppModule::DeleteSandBox(this);
  RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WUSA", L"WUSACommandLine");
  v9 = (void *)*((_QWORD *)this + 3);
  if ( !v9 || SetEvent(v9) )
  {
    v10 = (void *)*((_QWORD *)this + 4);
    if ( v10 )
      WaitForSingleObject(v10, 0xFFFFFFFF);
    v11 = (OLECHAR *)*((_QWORD *)this + 20);
    if ( v11 )
    {
      SysFreeString(v11);
      *((_QWORD *)this + 20) = 0;
    }
    v12 = (char *)*((_QWORD *)this + 23);
    if ( v12 != (char *)this + 192 && v12 )
    {
      operator delete(v12);
      *((_QWORD *)this + 23) = 0;
    }
  }
  else
  {
    WusaLogDebugEventA(L"AppModule::Uninit", 278, "Failed to set done event to release shutdown block");
  }
  v13 = (void *)*((_QWORD *)this + 3);
  if ( v13 )
  {
    CloseHandle(v13);
    *((_QWORD *)this + 3) = 0;
  }
  if ( RegHandle )
    EventUnregister(RegHandle);
  v14 = (void *)*((_QWORD *)this + 30);
  if ( v14 != (void *)-1LL )
  {
    CloseHandle(v14);
    *((_QWORD *)this + 30) = -1;
  }
}

```

## disassembly

```asm
0x1400108dc  mov     [rsp+arg_0], rbx
0x1400108e1  push    rdi
0x1400108e2  sub     rsp, 20h
0x1400108e6  xor     edi, edi
0x1400108e8  mov     rbx, rcx
0x1400108eb  cmp     [rcx+68h], edi
0x1400108ee  jnz     short loc_14001094F
0x1400108f0  mov     rcx, [rcx+28h]; hMem
0x1400108f4  test    rcx, rcx
0x1400108f7  jz      short loc_140010903
0x1400108f9  call    cs:__imp_LocalFree
0x1400108ff  mov     [rbx+28h], rdi
0x140010903  mov     rcx, [rbx+30h]; hMem
0x140010907  test    rcx, rcx
0x14001090a  jz      short loc_140010916
0x14001090c  call    cs:__imp_LocalFree
0x140010912  mov     [rbx+30h], rdi
0x140010916  mov     rcx, [rbx+38h]; hMem
0x14001091a  test    rcx, rcx
0x14001091d  jz      short loc_140010929
0x14001091f  call    cs:__imp_LocalFree
0x140010925  mov     [rbx+38h], rdi
0x140010929  mov     rcx, [rbx+40h]; hMem
0x14001092d  test    rcx, rcx
0x140010930  jz      short loc_14001093C
0x140010932  call    cs:__imp_LocalFree
0x140010938  mov     [rbx+40h], rdi
0x14001093c  mov     rcx, [rbx+48h]; hMem
0x140010940  test    rcx, rcx
0x140010943  jz      short loc_14001094F
0x140010945  call    cs:__imp_LocalFree
0x14001094b  mov     [rbx+48h], rdi
0x14001094f  cmp     [rbx+128h], edi
0x140010955  jz      short loc_140010964
0x140010957  lea     rcx, [rbx+100h]; lpCriticalSection
0x14001095e  call    cs:__imp_DeleteCriticalSection
0x140010964  cmp     [rbx+0ECh], edi
0x14001096a  jnz     short loc_14001097C
0x14001096c  call    cs:__imp_CoUninitialize
0x140010972  mov     dword ptr [rbx+0ECh], 1
0x14001097c  mov     rcx, [rbx+98h]; bstrString
0x140010983  test    rcx, rcx
0x140010986  jz      short loc_140010995
0x140010988  call    cs:__imp_SysFreeString
0x14001098e  mov     [rbx+98h], rdi
0x140010995  mov     rcx, [rbx+0C8h]; Block
0x14001099c  test    rcx, rcx
0x14001099f  jz      short loc_1400109AD
0x1400109a1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400109a6  mov     [rbx+0C8h], rdi
0x1400109ad  mov     rcx, rbx; this
0x1400109b0  call    ?DeleteSandBox@AppModule@@QEAAXXZ; AppModule::DeleteSandBox(void)
0x1400109b5  lea     r8, aWusacommandlin_0; "WUSACommandLine"
0x1400109bc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400109c3  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400109ca  call    cs:__imp_RegDeleteKeyValueW
0x1400109d0  mov     rcx, [rbx+18h]; hEvent
0x1400109d4  test    rcx, rcx
0x1400109d7  jz      short loc_1400109FD
0x1400109d9  call    cs:__imp_SetEvent
0x1400109df  test    eax, eax
0x1400109e1  jnz     short loc_1400109FD
0x1400109e3  lea     r8, aFailedToSetDon; "Failed to set done event to release shu"...
0x1400109ea  mov     edx, 116h
0x1400109ef  lea     rcx, aAppmoduleUnini; "AppModule::Uninit"
0x1400109f6  call    WusaLogDebugEventA
0x1400109fb  jmp     short loc_140010A4C
0x1400109fd  mov     rcx, [rbx+20h]; hHandle
0x140010a01  test    rcx, rcx
0x140010a04  jz      short loc_140010A0F
0x140010a06  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140010a09  call    cs:__imp_WaitForSingleObject
0x140010a0f  mov     rcx, [rbx+0A0h]; bstrString
0x140010a16  test    rcx, rcx
0x140010a19  jz      short loc_140010A28
0x140010a1b  call    cs:__imp_SysFreeString
0x140010a21  mov     [rbx+0A0h], rdi
0x140010a28  mov     rcx, [rbx+0B8h]; Block
0x140010a2f  lea     rax, [rbx+0C0h]
0x140010a36  cmp     rcx, rax
0x140010a39  jz      short loc_140010A4C
0x140010a3b  test    rcx, rcx
0x140010a3e  jz      short loc_140010A4C
0x140010a40  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140010a45  mov     [rbx+0B8h], rdi
0x140010a4c  mov     rcx, [rbx+18h]; hObject
0x140010a50  test    rcx, rcx
0x140010a53  jz      short loc_140010A5F
0x140010a55  call    cs:__imp_CloseHandle
0x140010a5b  mov     [rbx+18h], rdi
0x140010a5f  mov     rcx, cs:RegHandle; RegHandle
0x140010a66  test    rcx, rcx
0x140010a69  jz      short loc_140010A71
0x140010a6b  call    cs:__imp_EventUnregister
0x140010a71  mov     rcx, [rbx+0F0h]; hObject
0x140010a78  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140010a7c  jz      short loc_140010A8F
0x140010a7e  call    cs:__imp_CloseHandle
0x140010a84  mov     qword ptr [rbx+0F0h], 0FFFFFFFFFFFFFFFFh
0x140010a8f  mov     rbx, [rsp+28h+arg_0]
0x140010a94  add     rsp, 20h
0x140010a98  pop     rdi
0x140010a99  retn
```
