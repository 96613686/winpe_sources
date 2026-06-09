# LaunchModalElevatedAction(HWND__ *,SecurityAction)

- ea: `0x1800072a4`
- end: `0x180007414`
- name: `?LaunchModalElevatedAction@@YA_NPEAUHWND__@@W4SecurityAction@@@Z`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006520`

## callees

- `0x18000592c`
- `0x180006340`
- `0x1800063fc`
- `0x1800072a4`
- `0x18000a616`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007323`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007323`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007396`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007396`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800072c4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800072c4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800073f3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800073f3`

## pseudocode

```c
bool __fastcall LaunchModalElevatedAction(HWND a1, unsigned int a2)
{
  const struct _GUID *v4; // rdx
  const struct _GUID *v5; // r8
  int v6; // eax
  int v7; // ebx
  __int64 v8; // r8
  int v10; // [rsp+40h] [rbp-59h] BYREF
  HWND v11; // [rsp+44h] [rbp-55h]
  HINSTANCE v12; // [rsp+4Ch] [rbp-4Dh]
  int v13; // [rsp+54h] [rbp-45h]
  int v14; // [rsp+58h] [rbp-41h]
  __int64 v15; // [rsp+5Ch] [rbp-3Dh]
  __int64 v16; // [rsp+64h] [rbp-35h]
  __int64 v17; // [rsp+6Ch] [rbp-2Dh]
  HLOCAL v18; // [rsp+74h] [rbp-25h]
  _BYTE v19[116]; // [rsp+7Ch] [rbp-1Dh] BYREF
  void *v20; // [rsp+110h] [rbp+77h] BYREF
  HLOCAL Buffer; // [rsp+118h] [rbp+7Fh] BYREF

  CoInitializeEx(0, 2u);
  v20 = 0;
  v6 = CoCreateInstanceAsAdmin(a1, v4, v5, &v20);
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( v20 )
    {
      if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v20 + 24LL))(v20) == -2147024891 )
      {
        SecurityLogicControl::ShowFailDlg(a1, 1165);
        return 0;
      }
      v7 = (*(__int64 (__fastcall **)(void *, HWND, _QWORD))(*(_QWORD *)v20 + 32LL))(v20, a1, a2);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
    }
  }
  else if ( v6 != -2147023673 )
  {
    Buffer = 0;
    if ( FormatMessageW(0x1100u, 0, (unsigned __int16)v6, 0, (LPWSTR)&Buffer, 0, 0) )
    {
      v12 = hInstance;
      v10 = 160;
      v11 = a1;
      v13 = 8;
      v14 = 32;
      v15 = 1183;
      v17 = 1299;
      v18 = Buffer;
      memset_0(v19, 0, 0x64u);
      v16 = 65534;
      IsolationAwareTaskDialogIndirect((__int64)&v10, 0, v8, 0);
      LocalFree(Buffer);
    }
  }
  CoUninitialize();
  return v7 >= 0;
}

```

## disassembly

```asm
0x1800072a4  mov     [rsp-8+arg_0], rbx
0x1800072a9  push    rbp
0x1800072aa  push    rsi
0x1800072ab  push    rdi
0x1800072ac  lea     rbp, [rsp-47h]
0x1800072b1  sub     rsp, 0E0h
0x1800072b8  mov     esi, edx
0x1800072ba  mov     rdi, rcx
0x1800072bd  mov     edx, 2; dwCoInit
0x1800072c2  xor     ecx, ecx; pvReserved
0x1800072c4  call    cs:__imp_CoInitializeEx
0x1800072ca  lea     r9, [rbp+57h+arg_10]; void **
0x1800072ce  mov     [rbp+57h+arg_10], 0
0x1800072d6  mov     rcx, rdi; HWND
0x1800072d9  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x1800072de  mov     ebx, eax
0x1800072e0  test    eax, eax
0x1800072e2  jns     loc_18000739E
0x1800072e8  cmp     eax, 800704C7h
0x1800072ed  jz      loc_1800073F3
0x1800072f3  movzx   r8d, ax; dwMessageId
0x1800072f7  xor     r9d, r9d; dwLanguageId
0x1800072fa  lea     rax, [rbp+57h+Buffer]
0x1800072fe  mov     [rsp+0F0h+Arguments], 0; Arguments
0x180007307  mov     [rsp+0F0h+nSize], 0; nSize
0x18000730f  xor     edx, edx; lpSource
0x180007311  mov     ecx, 1100h; dwFlags
0x180007316  mov     [rsp+0F0h+lpBuffer], rax; lpBuffer
0x18000731b  mov     [rbp+57h+Buffer], 0
0x180007323  call    cs:__imp_FormatMessageW
0x180007329  test    eax, eax
0x18000732b  jz      loc_1800073F3
0x180007331  mov     rax, cs:hInstance
0x180007338  lea     rcx, [rbp+57h+var_74]; void *
0x18000733c  xor     edx, edx; Val
0x18000733e  mov     [rbp+57h+var_A4], rax
0x180007342  mov     rax, [rbp+57h+Buffer]
0x180007346  mov     [rbp+57h+var_B0], 0A0h
0x18000734d  mov     [rbp+57h+var_AC], rdi
0x180007351  lea     r8d, [rdx+64h]; Size
0x180007355  mov     [rbp+57h+var_9C], 8
0x18000735c  mov     [rbp+57h+var_98], 20h ; ' '
0x180007363  mov     [rbp+57h+var_94], 49Fh
0x18000736b  mov     [rbp+57h+var_84], 513h
0x180007373  mov     [rbp+57h+var_7C], rax
0x180007377  call    memset_0
0x18000737c  xor     r9d, r9d
0x18000737f  mov     [rbp+57h+var_8C], 0FFFEh
0x180007387  xor     edx, edx
0x180007389  lea     rcx, [rbp+57h+var_B0]
0x18000738d  call    IsolationAwareTaskDialogIndirect
0x180007392  mov     rcx, [rbp+57h+Buffer]; hMem
0x180007396  call    cs:__imp_LocalFree
0x18000739c  jmp     short loc_1800073F3
0x18000739e  mov     rcx, [rbp+57h+arg_10]
0x1800073a2  test    rcx, rcx
0x1800073a5  jz      short loc_1800073F3
0x1800073a7  mov     rax, [rcx]
0x1800073aa  mov     rax, [rax+18h]
0x1800073ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073b3  cmp     eax, 80070005h
0x1800073b8  jnz     short loc_1800073CB
0x1800073ba  mov     edx, 48Dh; int
0x1800073bf  mov     rcx, rdi; HWND
0x1800073c2  call    ?ShowFailDlg@SecurityLogicControl@@SAHPEAUHWND__@@H@Z; SecurityLogicControl::ShowFailDlg(HWND__ *,int)
0x1800073c7  xor     al, al
0x1800073c9  jmp     short loc_180007401
0x1800073cb  mov     rcx, [rbp+57h+arg_10]
0x1800073cf  mov     r8d, esi
0x1800073d2  mov     rdx, rdi
0x1800073d5  mov     rax, [rcx]
0x1800073d8  mov     rax, [rax+20h]
0x1800073dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073e1  mov     rcx, [rbp+57h+arg_10]
0x1800073e5  mov     ebx, eax
0x1800073e7  mov     rax, [rcx]
0x1800073ea  mov     rax, [rax+10h]
0x1800073ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073f3  call    cs:__imp_CoUninitialize
0x1800073f9  shr     ebx, 1Fh
0x1800073fc  xor     bl, 1
0x1800073ff  mov     al, bl
0x180007401  mov     rbx, [rsp+0F0h+arg_0]
0x180007409  add     rsp, 0E0h
0x180007410  pop     rdi
0x180007411  pop     rsi
0x180007412  pop     rbp
0x180007413  retn
```
