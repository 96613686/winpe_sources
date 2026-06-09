# HTTP_LOG_SITE_ENTRY::CreateConfigContext(IAppHostElement *,int,HTTP_LOG_FILE_CONFIG * *)

- ea: `0x1800073e8`
- end: `0x1800075bf`
- name: `?CreateConfigContext@HTTP_LOG_SITE_ENTRY@@AEAAJPEAUIAppHostElement@@HPEAPEAVHTTP_LOG_FILE_CONFIG@@@Z`
- size: `471`
- prototype: `__int64 __fastcall(HTTP_LOG_SITE_ENTRY *this, struct IAppHostElement *, int, struct IAppHostElement **)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x180007984`
- `0x180007cf0`

## callees

- `0x180001008`
- `0x180001048`
- `0x180002008`
- `0x180006f4c`
- `0x180007170`
- `0x180007294`
- `0x1800073e8`
- `0x180007744`
- `0x18000e97a`
- `0x18000e9a0`
- `0x180010010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000751d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007527`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007571`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000757b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000758f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000751d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007527`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007571`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000757b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000758f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007446`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007446`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180007513`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180007567`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180007513`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180007567`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_SITE_ENTRY::CreateConfigContext(
        HTTP_LOG_SITE_ENTRY *this,
        struct IAppHostElement *a2,
        int a3,
        struct IAppHostElement **a4)
{
  int DWORDProperty; // ebx
  struct IAppHostElement *v8; // rbx
  unsigned __int16 *v9; // r14
  struct IAppHostElement *v10; // rax
  struct IAppHostElement *v11; // rdi
  unsigned int Value; // [rsp+30h] [rbp-D0h] BYREF
  struct IAppHostElement *v14[2]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v15[32]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v16; // [rsp+68h] [rbp-98h]
  unsigned __int16 v17[64]; // [rsp+80h] [rbp-80h] BYREF

  v14[0] = 0;
  Value = 0;
  memset_0(v17, 0, sizeof(v17));
  STRU::STRU((STRU *)v15, v17, 0x40u);
  if ( a2 )
  {
    DWORDProperty = Config_GetDWORDProperty(a2, L"id", &Value);
    if ( DWORDProperty >= 0 )
    {
      DWORDProperty = Config_GetStringProperty(a2, L"name", (struct STRU *)v15);
      if ( DWORDProperty >= 0 )
      {
        DWORDProperty = Config_GetSubElement(a2, L"logFile", v14);
        if ( DWORDProperty >= 0 )
        {
          v8 = v14[0];
          v9 = v16;
          v10 = (struct IAppHostElement *)operator new(0xE8u);
          v11 = v10;
          v14[1] = v10;
          if ( v10 )
            HTTP_LOG_FILE_CONFIG_CONTEXT::HTTP_LOG_FILE_CONFIG_CONTEXT((HTTP_LOG_FILE_CONFIG_CONTEXT *)v10);
          else
            v11 = 0;
          if ( v11 )
          {
            DWORDProperty = HTTP_LOG_FILE_CONFIG::Initialize((HTTP_LOG_FILE_CONFIG *)v11, Value, v9, a3, v8);
            if ( DWORDProperty >= 0 )
            {
              *a4 = v11;
            }
            else
            {
              MULTISZ::~MULTISZ((MULTISZ *)&v11[20]);
              STRU::~STRU((STRU *)&v11[13]);
              STRU::~STRU((STRU *)&v11[6]);
              operator delete(v11);
            }
          }
          else
          {
            DWORDProperty = -2147024882;
          }
        }
      }
    }
  }
  else
  {
    DWORDProperty = -2147024809;
  }
  if ( v14[0] )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v14[0]->lpVtbl->Release)(v14[0]);
    v14[0] = 0;
  }
  STRU::~STRU((STRU *)v15);
  return (unsigned int)DWORDProperty;
}

```

## disassembly

```asm
0x1800073e8  mov     [rsp-8+arg_0], rbx
0x1800073ed  mov     [rsp-8+arg_10], rsi
0x1800073f2  push    rbp
0x1800073f3  push    rdi
0x1800073f4  push    r12
0x1800073f6  push    r14
0x1800073f8  push    r15
0x1800073fa  lea     rbp, [rsp-10h]
0x1800073ff  sub     rsp, 110h
0x180007406  mov     rax, cs:__security_cookie
0x18000740d  xor     rax, rsp
0x180007410  mov     [rbp+30h+var_30], rax
0x180007414  mov     r15, r9
0x180007417  mov     r12d, r8d
0x18000741a  mov     rdi, rdx
0x18000741d  xor     esi, esi
0x18000741f  mov     [rsp+130h+var_F8], rsi
0x180007424  mov     [rsp+130h+Value], esi
0x180007428  xor     edx, edx; Val
0x18000742a  mov     r8d, 80h; Size
0x180007430  lea     rcx, [rbp+30h+var_B0]; void *
0x180007434  call    memset_0
0x180007439  lea     r8d, [rsi+40h]
0x18000743d  lea     rdx, [rbp+30h+var_B0]
0x180007441  lea     rcx, [rsp+130h+var_E8]
0x180007446  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000744c  nop
0x18000744d  test    rdi, rdi
0x180007450  jnz     short loc_18000745C
0x180007452  mov     ebx, 80070057h
0x180007457  jmp     loc_18000753C
0x18000745c  lea     r8, [rsp+130h+Value]; unsigned int *
0x180007461  lea     rdx, aId; "id"
0x180007468  mov     rcx, rdi; struct IAppHostElement *
0x18000746b  call    ?Config_GetDWORDProperty@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; Config_GetDWORDProperty(IAppHostElement *,ushort const *,ulong *)
0x180007470  mov     ebx, eax
0x180007472  test    eax, eax
0x180007474  js      loc_18000753C
0x18000747a  lea     r8, [rsp+130h+var_E8]; struct STRU *
0x18000747f  lea     rdx, aName; "name"
0x180007486  mov     rcx, rdi; struct IAppHostElement *
0x180007489  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAVSTRU@@@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,STRU *)
0x18000748e  mov     ebx, eax
0x180007490  test    eax, eax
0x180007492  js      loc_18000753C
0x180007498  lea     r8, [rsp+130h+var_F8]; struct IAppHostElement **
0x18000749d  lea     rdx, aLogfile; "logFile"
0x1800074a4  mov     rcx, rdi; struct IAppHostElement *
0x1800074a7  call    ?Config_GetSubElement@@YAJPEAUIAppHostElement@@PEBGPEAPEAU1@@Z; Config_GetSubElement(IAppHostElement *,ushort const *,IAppHostElement * *)
0x1800074ac  mov     ebx, eax
0x1800074ae  test    eax, eax
0x1800074b0  js      loc_18000753C
0x1800074b6  mov     rbx, [rsp+130h+var_F8]
0x1800074bb  mov     r14, [rsp+130h+var_C8]
0x1800074c0  mov     ecx, 0E8h; Size
0x1800074c5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800074ca  mov     rdi, rax
0x1800074cd  mov     [rsp+130h+var_F0], rax
0x1800074d2  test    rax, rax
0x1800074d5  jz      short loc_1800074E1
0x1800074d7  mov     rcx, rax; this
0x1800074da  call    ??0HTTP_LOG_FILE_CONFIG_CONTEXT@@QEAA@XZ; HTTP_LOG_FILE_CONFIG_CONTEXT::HTTP_LOG_FILE_CONFIG_CONTEXT(void)
0x1800074df  jmp     short loc_1800074E3
0x1800074e1  xor     edi, edi
0x1800074e3  test    rdi, rdi
0x1800074e6  jnz     short loc_1800074EF
0x1800074e8  mov     ebx, 8007000Eh
0x1800074ed  jmp     short loc_18000753C
0x1800074ef  mov     [rsp+130h+var_110], rbx; struct IAppHostElement *
0x1800074f4  mov     r9d, r12d; int
0x1800074f7  mov     r8, r14; unsigned __int16 *
0x1800074fa  mov     edx, [rsp+130h+Value]; Value
0x1800074fe  mov     rcx, rdi; this
0x180007501  call    ?Initialize@HTTP_LOG_FILE_CONFIG@@AEAAJKPEBGHPEAUIAppHostElement@@@Z; HTTP_LOG_FILE_CONFIG::Initialize(ulong,ushort const *,int,IAppHostElement *)
0x180007506  mov     ebx, eax
0x180007508  test    eax, eax
0x18000750a  jns     short loc_180007537
0x18000750c  lea     rcx, [rdi+0A0h]
0x180007513  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180007519  lea     rcx, [rdi+68h]
0x18000751d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007523  lea     rcx, [rdi+30h]
0x180007527  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000752d  mov     rcx, rdi; Block
0x180007530  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007535  jmp     short loc_18000753A
0x180007537  mov     [r15], rdi
0x18000753a  xor     esi, esi
0x18000753c  mov     rcx, [rsp+130h+var_F8]
0x180007541  test    rcx, rcx
0x180007544  jz      short loc_18000755B
0x180007546  mov     rax, [rcx]
0x180007549  mov     rax, [rax+10h]
0x18000754d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007552  mov     [rsp+130h+var_F8], 0
0x18000755b  test    rsi, rsi
0x18000755e  jz      short loc_18000758A
0x180007560  lea     rcx, [rsi+0A0h]
0x180007567  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18000756d  lea     rcx, [rsi+68h]
0x180007571  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007577  lea     rcx, [rsi+30h]
0x18000757b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007581  mov     rcx, rsi; Block
0x180007584  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007589  nop
0x18000758a  lea     rcx, [rsp+130h+var_E8]
0x18000758f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007595  mov     eax, ebx
0x180007597  mov     rcx, [rbp+30h+var_30]
0x18000759b  xor     rcx, rsp; StackCookie
0x18000759e  call    __security_check_cookie
0x1800075a3  lea     r11, [rsp+130h+var_20]
0x1800075ab  mov     rbx, [r11+30h]
0x1800075af  mov     rsi, [r11+40h]
0x1800075b3  mov     rsp, r11
0x1800075b6  pop     r15
0x1800075b8  pop     r14
0x1800075ba  pop     r12
0x1800075bc  pop     rdi
0x1800075bd  pop     rbp
0x1800075be  retn
```
