# LOG_SVC_ADMIN::GetPipeClient(char const *,int,HTTP_LOG_PIPE_CLIENT * *)

- ea: `0x18000b964`
- end: `0x18000bc5c`
- name: `?GetPipeClient@LOG_SVC_ADMIN@@QEAAJPEBDHPEAPEAVHTTP_LOG_PIPE_CLIENT@@@Z`
- size: `760`
- prototype: `__int64 __fastcall(LOG_SVC_ADMIN *this, char *, int, struct HTTP_LOG_PIPE_CLIENT **)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a57c`

## callees

- `0x180001008`
- `0x180009148`
- `0x1800097f8`
- `0x180009c84`
- `0x18000a90c`
- `0x18000b77c`
- `0x18000b964`
- `0x18000c46c`
- `0x18000e97a`
- `0x18000e9a0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bc2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bc2d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000bb2b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000bb2b`
- `iisutil!PuDbgPrint` at `0x18000bb6f`
- `iisutil!PuDbgPrint` at `0x18000bbbf`
- `iisutil!PuDbgPrint` at `0x18000bb6f`
- `iisutil!PuDbgPrint` at `0x18000bbbf`

## string_xrefs

- `0x18000bb61`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000bbb1`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`

## pseudocode

```c
__int64 __fastcall LOG_SVC_ADMIN::GetPipeClient(
        LOG_SVC_ADMIN *this,
        char *a2,
        int a3,
        struct HTTP_LOG_PIPE_CLIENT **a4)
{
  __int64 v8; // r8
  int v9; // edi
  int Item; // eax
  struct STTABLE_ITEM *v11; // rax
  HTTP_LOG_PIPE_CLIENT *v12; // rbx
  int v13; // eax
  int v14; // r14d
  struct STTABLE_ITEM *v16[2]; // [rsp+40h] [rbp-59h] BYREF
  void **v17; // [rsp+50h] [rbp-49h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-41h]
  int v19; // [rsp+60h] [rbp-39h]
  size_t Size; // [rsp+64h] [rbp-35h]
  _BYTE v21[64]; // [rsp+6Ch] [rbp-2Dh] BYREF
  __int16 v22; // [rsp+ACh] [rbp+13h]

  v17 = &STBUFF::`vftable';
  hMem = v21;
  v19 = 0;
  Size = 0x400000000040LL;
  memset_0(v21, 0, sizeof(v21));
  v22 = 0;
  v16[0] = 0;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  v9 = STBUFF::SetData((STBUFF *)&v17, a2, v8);
  if ( v9 < 0 )
    goto LABEL_38;
  Item = STTABLE::GetItem((LOG_SVC_ADMIN *)((char *)this + 1400), (struct STBUFF *)&v17, v16);
  v9 = Item;
  if ( Item < 0 )
  {
    if ( Item != -2147024894 || !a3 )
      goto LABEL_29;
    v9 = 0;
  }
  if ( v16[0] )
  {
    *a4 = v16[0];
    goto LABEL_38;
  }
  if ( a3 )
  {
    v11 = (struct STTABLE_ITEM *)operator new(0x13A10u);
    v16[0] = v11;
    if ( v11 )
      v12 = HTTP_LOG_PIPE_CLIENT::HTTP_LOG_PIPE_CLIENT(v11);
    else
      v12 = 0;
    if ( !v12 )
    {
      v9 = -2147024882;
LABEL_35:
      if ( v12 && _InterlockedExchangeAdd((volatile signed __int32 *)v12 + 6, 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(HTTP_LOG_PIPE_CLIENT *, __int64))v12)(v12, 1);
      goto LABEL_38;
    }
    v9 = HTTP_LOG_PIPE_CLIENT::Initialize(v12, a2);
    if ( v9 < 0 )
      goto LABEL_35;
    v13 = HTTP_LOG_PIPE_CLIENT::ConnectToPipe(v12);
    v9 = v13;
    if ( v13 >= 0 )
    {
      v9 = STTABLE::Insert((LOG_SVC_ADMIN *)((char *)this + 1400), v12);
      if ( v9 >= 0 )
      {
LABEL_34:
        *a4 = v12;
        v12 = 0;
      }
      goto LABEL_35;
    }
    if ( v13 != -2147024665 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
          2115,
          "LOG_SVC_ADMIN::GetPipeClient",
          "Connect to pipe %s failed with %08x\n",
          a2,
          v13);
      ++*((_DWORD *)this + 470);
      *((_DWORD *)this + 471) = v9;
      goto LABEL_35;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 + 6, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(HTTP_LOG_PIPE_CLIENT *, __int64))v12)(v12, 1);
    v16[0] = 0;
    v14 = 0;
    while ( 1 )
    {
      v9 = STTABLE::GetItem((LOG_SVC_ADMIN *)((char *)this + 1400), (struct STBUFF *)&v17, v16);
      if ( ((v9 + 0x80000000) & 0x80000000) == 0 && v9 != -2147024894 )
        break;
      v12 = v16[0];
      if ( v16[0] )
        goto LABEL_34;
      Sleep(0x1F4u);
      if ( (unsigned int)++v14 >= 0xA )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
            2105,
            "LOG_SVC_ADMIN::GetPipeClient",
            "Couldn't connect to pipe for %s\n",
            a2);
        ++*((_DWORD *)this + 470);
        goto LABEL_38;
      }
    }
LABEL_29:
    v12 = v16[0];
    goto LABEL_35;
  }
LABEL_38:
  v17 = &STBUFF::`vftable';
  if ( hMem != v21 )
    LocalFree(hMem);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000b964  mov     [rsp-8+arg_10], rbx
0x18000b969  push    rbp
0x18000b96a  push    rsi
0x18000b96b  push    rdi
0x18000b96c  push    r12
0x18000b96e  push    r13
0x18000b970  push    r14
0x18000b972  push    r15
0x18000b974  lea     rbp, [rsp-27h]
0x18000b979  sub     rsp, 0C0h
0x18000b980  mov     rax, cs:__security_cookie
0x18000b987  xor     rax, rsp
0x18000b98a  mov     [rbp+57h+var_40], rax
0x18000b98e  mov     r13, r9
0x18000b991  mov     ebx, r8d
0x18000b994  mov     r15, rdx
0x18000b997  mov     rsi, rcx
0x18000b99a  lea     rax, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x18000b9a1  mov     [rbp+57h+var_A0], rax
0x18000b9a5  lea     rax, [rbp+57h+var_84]
0x18000b9a9  mov     [rbp+57h+hMem], rax
0x18000b9ad  mov     [rbp+57h+var_90], 0
0x18000b9b4  mov     r8d, 40h ; '@'; Size
0x18000b9ba  mov     dword ptr [rbp+57h+Size], r8d
0x18000b9be  mov     dword ptr [rbp+57h+Size+4], 4000h
0x18000b9c5  xor     edx, edx; Val
0x18000b9c7  lea     rcx, [rbp+57h+var_84]; void *
0x18000b9cb  call    memset_0
0x18000b9d0  lea     rax, [rbp+57h+var_84]
0x18000b9d4  mov     rcx, [rbp+57h+hMem]; void *
0x18000b9d8  cmp     rcx, rax
0x18000b9db  jz      short loc_18000B9E8
0x18000b9dd  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x18000b9e1  xor     edx, edx; Val
0x18000b9e3  call    memset_0
0x18000b9e8  mov     [rbp+57h+var_44], 0
0x18000b9ee  mov     [rbp+57h+var_B0], 0
0x18000b9f6  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000b9fa  inc     r8; unsigned int
0x18000b9fd  cmp     byte ptr [r15+r8], 0
0x18000ba02  jnz     short loc_18000B9FA
0x18000ba04  mov     rdx, r15; void *
0x18000ba07  lea     rcx, [rbp+57h+var_A0]; this
0x18000ba0b  call    ?SetData@STBUFF@@QEAAJPEAXK@Z; STBUFF::SetData(void *,ulong)
0x18000ba10  mov     edi, eax
0x18000ba12  test    eax, eax
0x18000ba14  js      loc_18000BC15
0x18000ba1a  lea     r12, [rsi+578h]
0x18000ba21  lea     r8, [rbp+57h+var_B0]; struct STTABLE_ITEM **
0x18000ba25  lea     rdx, [rbp+57h+var_A0]; struct STBUFF *
0x18000ba29  mov     rcx, r12; this
0x18000ba2c  call    ?GetItem@STTABLE@@QEAAJPEAVSTBUFF@@PEAPEAVSTTABLE_ITEM@@@Z; STTABLE::GetItem(STBUFF *,STTABLE_ITEM * *)
0x18000ba31  mov     edi, eax
0x18000ba33  test    eax, eax
0x18000ba35  jns     short loc_18000BA4C
0x18000ba37  cmp     eax, 80070002h
0x18000ba3c  jnz     loc_18000BB80
0x18000ba42  test    ebx, ebx
0x18000ba44  jz      loc_18000BB80
0x18000ba4a  xor     edi, edi
0x18000ba4c  mov     rax, [rbp+57h+var_B0]
0x18000ba50  test    rax, rax
0x18000ba53  jz      short loc_18000BA5E
0x18000ba55  mov     [r13+0], rax
0x18000ba59  jmp     loc_18000BC15
0x18000ba5e  test    ebx, ebx
0x18000ba60  jz      loc_18000BC15
0x18000ba66  mov     ecx, 13A10h; Size
0x18000ba6b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ba70  mov     [rbp+57h+var_B0], rax
0x18000ba74  test    rax, rax
0x18000ba77  jz      short loc_18000BA86
0x18000ba79  mov     rcx, rax; this
0x18000ba7c  call    ??0HTTP_LOG_PIPE_CLIENT@@QEAA@XZ; HTTP_LOG_PIPE_CLIENT::HTTP_LOG_PIPE_CLIENT(void)
0x18000ba81  mov     rbx, rax
0x18000ba84  jmp     short loc_18000BA88
0x18000ba86  xor     ebx, ebx
0x18000ba88  test    rbx, rbx
0x18000ba8b  jnz     short loc_18000BA97
0x18000ba8d  mov     edi, 8007000Eh
0x18000ba92  jmp     loc_18000BBEA
0x18000ba97  mov     rdx, r15; char *
0x18000ba9a  mov     rcx, rbx; pv
0x18000ba9d  call    ?Initialize@HTTP_LOG_PIPE_CLIENT@@QEAAJPEBD@Z; HTTP_LOG_PIPE_CLIENT::Initialize(char const *)
0x18000baa2  mov     edi, eax
0x18000baa4  test    eax, eax
0x18000baa6  js      loc_18000BBEA
0x18000baac  mov     rcx, rbx; this
0x18000baaf  call    ?ConnectToPipe@HTTP_LOG_PIPE_CLIENT@@QEAAJXZ; HTTP_LOG_PIPE_CLIENT::ConnectToPipe(void)
0x18000bab4  mov     edi, eax
0x18000bab6  test    eax, eax
0x18000bab8  jns     loc_18000BBD3
0x18000babe  cmp     eax, 800700E7h
0x18000bac3  jnz     loc_18000BB86
0x18000bac9  or      eax, 0FFFFFFFFh
0x18000bacc  lock xadd [rbx+18h], eax
0x18000bad1  cmp     eax, 1
0x18000bad4  jnz     short loc_18000BAE9
0x18000bad6  mov     rax, [rbx]
0x18000bad9  mov     edx, 1
0x18000bade  mov     rcx, rbx
0x18000bae1  mov     rax, [rax]
0x18000bae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bae9  mov     [rbp+57h+var_B0], 0
0x18000baf1  xor     r14d, r14d
0x18000baf4  mov     ebx, 80000000h
0x18000baf9  lea     r8, [rbp+57h+var_B0]; struct STTABLE_ITEM **
0x18000bafd  lea     rdx, [rbp+57h+var_A0]; struct STBUFF *
0x18000bb01  mov     rcx, r12; this
0x18000bb04  call    ?GetItem@STTABLE@@QEAAJPEAVSTBUFF@@PEAPEAVSTTABLE_ITEM@@@Z; STTABLE::GetItem(STBUFF *,STTABLE_ITEM * *)
0x18000bb09  mov     edi, eax
0x18000bb0b  add     eax, ebx
0x18000bb0d  test    ebx, eax
0x18000bb0f  jnz     short loc_18000BB19
0x18000bb11  cmp     edi, 80070002h
0x18000bb17  jnz     short loc_18000BB80
0x18000bb19  mov     rbx, [rbp+57h+var_B0]
0x18000bb1d  test    rbx, rbx
0x18000bb20  jnz     loc_18000BBE4
0x18000bb26  mov     ecx, 1F4h; dwMilliseconds
0x18000bb2b  call    cs:__imp_Sleep
0x18000bb31  inc     r14d
0x18000bb34  cmp     r14d, 0Ah
0x18000bb38  jb      short loc_18000BAF4
0x18000bb3a  test    byte ptr cs:g_dwDebugFlags, 3
0x18000bb41  jz      short loc_18000BB75
0x18000bb43  mov     [rsp+0F0h+var_C8], r15
0x18000bb48  lea     rax, aCouldnTConnect; "Couldn't connect to pipe for %s\n"
0x18000bb4f  mov     [rsp+0F0h+var_D0], rax
0x18000bb54  lea     r9, aLogSvcAdminGet; "LOG_SVC_ADMIN::GetPipeClient"
0x18000bb5b  mov     r8d, 839h
0x18000bb61  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000bb68  mov     rcx, cs:g_pDebug
0x18000bb6f  call    cs:__imp_PuDbgPrint
0x18000bb75  inc     dword ptr [rsi+758h]
0x18000bb7b  jmp     loc_18000BC15
0x18000bb80  mov     rbx, [rbp+57h+var_B0]
0x18000bb84  jmp     short loc_18000BBEA
0x18000bb86  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000bb8d  jz      short loc_18000BBC5
0x18000bb8f  mov     [rsp+0F0h+var_C0], edi
0x18000bb93  mov     [rsp+0F0h+var_C8], r15
0x18000bb98  lea     rax, aConnectToPipeS; "Connect to pipe %s failed with %08x\n"
0x18000bb9f  mov     [rsp+0F0h+var_D0], rax
0x18000bba4  lea     r9, aLogSvcAdminGet; "LOG_SVC_ADMIN::GetPipeClient"
0x18000bbab  mov     r8d, 843h
0x18000bbb1  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000bbb8  mov     rcx, cs:g_pDebug
0x18000bbbf  call    cs:__imp_PuDbgPrint
0x18000bbc5  inc     dword ptr [rsi+758h]
0x18000bbcb  mov     [rsi+75Ch], edi
0x18000bbd1  jmp     short loc_18000BBEA
0x18000bbd3  mov     rdx, rbx; struct STTABLE_ITEM *
0x18000bbd6  mov     rcx, r12; this
0x18000bbd9  call    ?Insert@STTABLE@@QEAAJPEAVSTTABLE_ITEM@@@Z; STTABLE::Insert(STTABLE_ITEM *)
0x18000bbde  mov     edi, eax
0x18000bbe0  test    eax, eax
0x18000bbe2  js      short loc_18000BBEA
0x18000bbe4  mov     [r13+0], rbx
0x18000bbe8  xor     ebx, ebx
0x18000bbea  test    rbx, rbx
0x18000bbed  jz      short loc_18000BC15
0x18000bbef  or      eax, 0FFFFFFFFh
0x18000bbf2  lock xadd [rbx+18h], eax
0x18000bbf7  cmp     eax, 1
0x18000bbfa  jnz     short loc_18000BC15
0x18000bbfc  test    rbx, rbx
0x18000bbff  jz      short loc_18000BC15
0x18000bc01  mov     rax, [rbx]
0x18000bc04  mov     edx, 1
0x18000bc09  mov     rcx, rbx
0x18000bc0c  mov     rax, [rax]
0x18000bc0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc14  nop
0x18000bc15  lea     rax, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x18000bc1c  mov     [rbp+57h+var_A0], rax
0x18000bc20  lea     rax, [rbp+57h+var_84]
0x18000bc24  mov     rcx, [rbp+57h+hMem]; hMem
0x18000bc28  cmp     rcx, rax
0x18000bc2b  jz      short loc_18000BC33
0x18000bc2d  call    cs:__imp_LocalFree
0x18000bc33  mov     eax, edi
0x18000bc35  mov     rcx, [rbp+57h+var_40]
0x18000bc39  xor     rcx, rsp; StackCookie
0x18000bc3c  call    __security_check_cookie
0x18000bc41  mov     rbx, [rsp+0F0h+arg_10]
0x18000bc49  add     rsp, 0C0h
0x18000bc50  pop     r15
0x18000bc52  pop     r14
0x18000bc54  pop     r13
0x18000bc56  pop     r12
0x18000bc58  pop     rdi
0x18000bc59  pop     rsi
0x18000bc5a  pop     rbp
0x18000bc5b  retn
```
