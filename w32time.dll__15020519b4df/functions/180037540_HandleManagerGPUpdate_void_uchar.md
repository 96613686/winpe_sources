# HandleManagerGPUpdate(void *,uchar)

- ea: `0x180037540`
- end: `0x180037681`
- name: `?HandleManagerGPUpdate@@YAXPEAXE@Z`
- size: `321`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000e620`
- `0x180018138`
- `0x18001d9a0`
- `0x180032ff0`
- `0x180037540`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180037550`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18003765e`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180037550`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18003765e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800375a7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800375a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800375b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800375b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037632`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18003761a`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18003761a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800375e6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800375e6`

## string_xrefs

- `0x180037572`: `W32TmServiceMain: Group Policy Update\n`

## pseudocode

```c
void __fastcall HandleManagerGPUpdate(void *a1)
{
  __int64 v1; // [rsp+90h] [rbp+18h]

  v1 = _set_se_translator(SeTransFunc);
  if ( (unsigned __int8)FileLogAllowEntry(72) )
    FileLogAdd(L"W32TmServiceMain: Group Policy Update\n");
  HandleManagerParamChange(0, 0);
  if ( (int)AllowShutdown(0) >= 0 )
  {
    if ( !ResetEvent(qword_1800A36E8) )
      goto LABEL_8;
    if ( qword_1800A3768 )
    {
      UnregisterWaitEx(qword_1800A3768, 0);
      qword_1800A3768 = 0;
    }
    qword_1800A3768 = (HANDLE)RegisterWaitForSingleObjectEx(qword_1800A36E8, HandleManagerGPUpdate, 0, 0xFFFFFFFFLL, 8);
    if ( qword_1800A3768 )
      _set_se_translator(v1);
    else
LABEL_8:
      GetLastError();
    AllowShutdown(1);
  }
}

```

## disassembly

```asm
0x180037540  sub     rsp, 78h
0x180037544  mov     [rsp+78h+var_48], 0
0x180037549  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x180037550  call    cs:__imp__set_se_translator
0x180037557  nop     dword ptr [rax+rax+00h]
0x18003755c  mov     [rsp+78h+arg_10], rax
0x180037564  mov     ecx, 48h ; 'H'
0x180037569  call    FileLogAllowEntry
0x18003756e  test    al, al
0x180037570  jz      short loc_18003757E
0x180037572  lea     rcx, aW32tmservicema_11; "W32TmServiceMain: Group Policy Update\n"
0x180037579  call    FileLogAdd
0x18003757e  xor     edx, edx; unsigned __int8
0x180037580  xor     ecx, ecx; void *
0x180037582  call    ?HandleManagerParamChange@@YAXPEAXE@Z; HandleManagerParamChange(void *,uchar)
0x180037587  xor     ecx, ecx; int
0x180037589  call    ?AllowShutdown@@YAJH@Z; AllowShutdown(int)
0x18003758e  mov     [rsp+78h+var_44], eax
0x180037592  test    eax, eax
0x180037594  jns     short loc_18003759B
0x180037596  jmp     loc_18003767B
0x18003759b  mov     [rsp+78h+var_48], 1
0x1800375a0  mov     rcx, cs:qword_1800A36E8; hEvent
0x1800375a7  call    cs:__imp_ResetEvent
0x1800375ae  nop     dword ptr [rax+rax+00h]
0x1800375b3  test    eax, eax
0x1800375b5  jnz     short loc_1800375D8
0x1800375b7  call    cs:__imp_GetLastError
0x1800375be  nop     dword ptr [rax+rax+00h]
0x1800375c3  test    eax, eax
0x1800375c5  jle     short loc_1800375CF
0x1800375c7  movzx   eax, ax
0x1800375ca  or      eax, 80070000h
0x1800375cf  mov     [rsp+78h+var_44], eax
0x1800375d3  jmp     loc_180037671
0x1800375d8  mov     rcx, cs:qword_1800A3768; WaitHandle
0x1800375df  test    rcx, rcx
0x1800375e2  jz      short loc_1800375FD
0x1800375e4  xor     edx, edx; CompletionEvent
0x1800375e6  call    cs:__imp_UnregisterWaitEx
0x1800375ed  nop     dword ptr [rax+rax+00h]
0x1800375f2  mov     cs:qword_1800A3768, 0
0x1800375fd  mov     [rsp+78h+var_58], 8
0x180037605  or      r9d, 0FFFFFFFFh
0x180037609  xor     r8d, r8d
0x18003760c  lea     rdx, ?HandleManagerGPUpdate@@YAXPEAXE@Z; HandleManagerGPUpdate(void *,uchar)
0x180037613  mov     rcx, cs:qword_1800A36E8
0x18003761a  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180037621  nop     dword ptr [rax+rax+00h]
0x180037626  mov     cs:qword_1800A3768, rax
0x18003762d  test    rax, rax
0x180037630  jnz     short loc_180037650
0x180037632  call    cs:__imp_GetLastError
0x180037639  nop     dword ptr [rax+rax+00h]
0x18003763e  test    eax, eax
0x180037640  jle     short loc_18003764A
0x180037642  movzx   eax, ax
0x180037645  or      eax, 80070000h
0x18003764a  mov     [rsp+78h+var_44], eax
0x18003764e  jmp     short loc_180037671
0x180037650  jmp     short loc_180037656
0x180037652  jmp     short loc_180037656
0x180037654  jmp     short $+2
0x180037656  mov     rcx, [rsp+78h+arg_10]
0x18003765e  call    cs:__imp__set_se_translator
0x180037665  nop     dword ptr [rax+rax+00h]
0x18003766a  cmp     [rsp+78h+var_48], 0
0x18003766f  jz      short loc_18003767B
0x180037671  mov     ecx, 1; int
0x180037676  call    ?AllowShutdown@@YAJH@Z; AllowShutdown(int)
0x18003767b  add     rsp, 78h
0x18003767f  retn
```
