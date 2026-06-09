# s_W32TimeSync

- ea: `0x1800123b0`
- end: `0x1800125ad`
- name: `s_W32TimeSync`
- size: `509`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180010748`
- `0x1800123b0`
- `0x1800125c0`
- `0x180018138`
- `0x18001d9a0`
- `0x180032ff0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800123c6`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180012587`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800123c6`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180012587`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800124e1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800124e1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012520`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012520`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800124f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012531`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800124f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012531`

## string_xrefs

- `0x180012465`: `RPC Call - UpdateAndResync\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall s_W32TimeSync(__int64 a1, int a2, char a3)
{
  char v5; // al
  int *v6; // rcx
  signed int LastError; // eax
  DWORD v8; // eax
  signed int v9; // eax
  int v11; // [rsp+20h] [rbp-58h]
  int v12; // [rsp+24h] [rbp-54h] BYREF
  int v13; // [rsp+28h] [rbp-50h] BYREF
  int v14; // [rsp+2Ch] [rbp-4Ch] BYREF
  __int64 v15; // [rsp+30h] [rbp-48h]
  int v16; // [rsp+98h] [rbp+20h] BYREF

  v15 = _set_se_translator(SeTransFunc);
  v5 = FileLogAllowEntry(69);
  if ( (a3 & 4) != 0 )
  {
    if ( v5 )
      FileLogAdd(L"RPC Call - Rediscover\n");
    v11 = HandleManagerNetTopoChange(0, 1, 0);
    if ( v11 < 0 )
      goto LABEL_36;
    byte_1800A46A0 = 1;
    v16 = 1;
    v6 = &v16;
    goto LABEL_18;
  }
  if ( (a3 & 1) != 0 )
  {
    if ( v5 )
      FileLogAdd(L"RPC Call - HardResync\n");
    byte_1800A46A0 = 1;
    v12 = 1;
    v6 = &v12;
LABEL_18:
    HandleManagerTimeSlip(v6);
    goto LABEL_25;
  }
  if ( (a3 & 8) != 0 )
  {
    if ( v5 )
      FileLogAdd(L"RPC Call - UpdateAndResync\n");
    HandleManagerParamChange(0);
    byte_1800A46A0 = 1;
    v13 = 1;
    v6 = &v13;
    goto LABEL_18;
  }
  if ( (a3 & 0x10) != 0 )
  {
    if ( v5 )
      FileLogAdd(L"RPC Call - ForceResync\n");
    byte_1800A46A0 = 1;
    v14 = 1;
    byte_1800A45C4 = 1;
    v6 = &v14;
    goto LABEL_18;
  }
  if ( v5 )
    FileLogAdd(L"RPC Call - SoftResync\n");
  if ( !SetEvent(qword_1800A3730) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = LastError;
    goto LABEL_36;
  }
LABEL_25:
  if ( a2 )
  {
    v8 = WaitForSingleObject(hHandle, 0xFFFFFFFF);
    if ( v8 == -1 )
    {
      v9 = GetLastError();
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      v11 = v9;
      goto LABEL_36;
    }
    if ( v8 == 258 )
    {
      v11 = 1;
      goto LABEL_36;
    }
  }
  v11 = 0;
  if ( a2 && (a3 & 2) != 0 )
    v11 = dword_1800A4690;
  _set_se_translator(v15);
LABEL_36:
  byte_1800A46A0 = 0;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800123b0  mov     [rsp+arg_0], rsi
0x1800123b5  push    rdi
0x1800123b6  sub     rsp, 70h
0x1800123ba  mov     edi, r8d
0x1800123bd  mov     esi, edx
0x1800123bf  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x1800123c6  call    cs:__imp__set_se_translator
0x1800123cd  nop     dword ptr [rax+rax+00h]
0x1800123d2  mov     [rsp+78h+var_48], rax
0x1800123d7  mov     ecx, 45h ; 'E'
0x1800123dc  call    FileLogAllowEntry
0x1800123e1  test    dil, 4
0x1800123e5  jz      short loc_18001242F
0x1800123e7  test    al, al
0x1800123e9  jz      short loc_1800123F7
0x1800123eb  lea     rcx, aRpcCallRedisco; "RPC Call - Rediscover\n"
0x1800123f2  call    FileLogAdd
0x1800123f7  xor     r8d, r8d
0x1800123fa  mov     dl, 1
0x1800123fc  xor     ecx, ecx
0x1800123fe  call    ?HandleManagerNetTopoChange@@YAJPEA_K_NW4_NetTopoChangeSource@@@Z; HandleManagerNetTopoChange(unsigned __int64 *,bool,_NetTopoChangeSource)
0x180012403  mov     [rsp+78h+var_58], eax
0x180012407  test    eax, eax
0x180012409  jns     short loc_180012410
0x18001240b  jmp     loc_180012593
0x180012410  mov     cs:byte_1800A46A0, 1
0x180012417  mov     [rsp+78h+arg_18], 1
0x180012422  lea     rcx, [rsp+78h+arg_18]
0x18001242a  jmp     loc_1800124C1
0x18001242f  test    dil, 1
0x180012433  jz      short loc_18001245B
0x180012435  test    al, al
0x180012437  jz      short loc_180012445
0x180012439  lea     rcx, aRpcCallHardres; "RPC Call - HardResync\n"
0x180012440  call    FileLogAdd
0x180012445  mov     cs:byte_1800A46A0, 1
0x18001244c  mov     [rsp+78h+var_54], 1
0x180012454  lea     rcx, [rsp+78h+var_54]
0x180012459  jmp     short loc_1800124C1
0x18001245b  test    dil, 8
0x18001245f  jz      short loc_180012490
0x180012461  test    al, al
0x180012463  jz      short loc_180012471
0x180012465  lea     rcx, aRpcCallUpdatea; "RPC Call - UpdateAndResync\n"
0x18001246c  call    FileLogAdd
0x180012471  xor     edx, edx; unsigned __int8
0x180012473  xor     ecx, ecx; void *
0x180012475  call    ?HandleManagerParamChange@@YAXPEAXE@Z; HandleManagerParamChange(void *,uchar)
0x18001247a  mov     cs:byte_1800A46A0, 1
0x180012481  mov     [rsp+78h+var_50], 1
0x180012489  lea     rcx, [rsp+78h+var_50]
0x18001248e  jmp     short loc_1800124C1
0x180012490  test    dil, 10h
0x180012494  jz      short loc_1800124CA
0x180012496  test    al, al
0x180012498  jz      short loc_1800124A6
0x18001249a  lea     rcx, aRpcCallForcere; "RPC Call - ForceResync\n"
0x1800124a1  call    FileLogAdd
0x1800124a6  mov     cs:byte_1800A46A0, 1
0x1800124ad  mov     [rsp+78h+var_4C], 1
0x1800124b5  mov     cs:byte_1800A45C4, 1
0x1800124bc  lea     rcx, [rsp+78h+var_4C]; void *
0x1800124c1  xor     edx, edx; unsigned __int8
0x1800124c3  call    ?HandleManagerTimeSlip@@YAXPEAXE@Z; HandleManagerTimeSlip(void *,uchar)
0x1800124c8  jmp     short loc_180012512
0x1800124ca  test    al, al
0x1800124cc  jz      short loc_1800124DA
0x1800124ce  lea     rcx, aRpcCallSoftres; "RPC Call - SoftResync\n"
0x1800124d5  call    FileLogAdd
0x1800124da  mov     rcx, cs:qword_1800A3730; hEvent
0x1800124e1  call    cs:__imp_SetEvent
0x1800124e8  nop     dword ptr [rax+rax+00h]
0x1800124ed  test    eax, eax
0x1800124ef  jnz     short loc_180012512
0x1800124f1  call    cs:__imp_GetLastError
0x1800124f8  nop     dword ptr [rax+rax+00h]
0x1800124fd  test    eax, eax
0x1800124ff  jle     short loc_180012509
0x180012501  movzx   eax, ax
0x180012504  or      eax, 80070000h
0x180012509  mov     [rsp+78h+var_58], eax
0x18001250d  jmp     loc_180012593
0x180012512  test    esi, esi
0x180012514  jz      short loc_180012560
0x180012516  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180012519  mov     rcx, cs:hHandle; hHandle
0x180012520  call    cs:__imp_WaitForSingleObject
0x180012527  nop     dword ptr [rax+rax+00h]
0x18001252c  cmp     eax, 0FFFFFFFFh
0x18001252f  jnz     short loc_18001254F
0x180012531  call    cs:__imp_GetLastError
0x180012538  nop     dword ptr [rax+rax+00h]
0x18001253d  test    eax, eax
0x18001253f  jle     short loc_180012549
0x180012541  movzx   eax, ax
0x180012544  or      eax, 80070000h
0x180012549  mov     [rsp+78h+var_58], eax
0x18001254d  jmp     short loc_180012593
0x18001254f  cmp     eax, 102h
0x180012554  jnz     short loc_180012560
0x180012556  mov     [rsp+78h+var_58], 1
0x18001255e  jmp     short loc_180012593
0x180012560  mov     [rsp+78h+var_58], 0
0x180012568  test    esi, esi
0x18001256a  jz      short loc_18001257C
0x18001256c  test    dil, 2
0x180012570  jz      short loc_18001257C
0x180012572  mov     eax, cs:dword_1800A4690
0x180012578  mov     [rsp+78h+var_58], eax
0x18001257c  jmp     short loc_180012582
0x18001257e  jmp     short loc_180012582
0x180012580  jmp     short $+2
0x180012582  mov     rcx, [rsp+78h+var_48]
0x180012587  call    cs:__imp__set_se_translator
0x18001258e  nop     dword ptr [rax+rax+00h]
0x180012593  mov     cs:byte_1800A46A0, 0
0x18001259a  mov     eax, [rsp+78h+var_58]
0x18001259e  mov     rsi, [rsp+78h+arg_0]
0x1800125a6  add     rsp, 70h
0x1800125aa  pop     rdi
0x1800125ab  retn
```
