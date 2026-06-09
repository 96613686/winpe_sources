# HTTP_LOG_FILE_CONFIG::CreateCentralLogConfigContext(IAppHostElement *,HTTP_LOG_FILE_CONFIG * *)

- ea: `0x180007338`
- end: `0x1800073df`
- name: `?CreateCentralLogConfigContext@HTTP_LOG_FILE_CONFIG@@SAJPEAUIAppHostElement@@PEAPEAV1@@Z`
- size: `167`
- prototype: `__int64 __fastcall(struct IAppHostElement *, struct HTTP_LOG_FILE_CONFIG **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180008230`
- `0x180008858`

## callees

- `0x180001008`
- `0x180001048`
- `0x180002008`
- `0x180006df8`
- `0x180007338`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180007397`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800073a1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007397`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800073a1`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000738d`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000738d`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_FILE_CONFIG::CreateCentralLogConfigContext(
        struct IAppHostElement *a1,
        struct HTTP_LOG_FILE_CONFIG **a2)
{
  HTTP_LOG_FILE_CONFIG_CONTEXT *v4; // rax
  int *v5; // rbx
  int BoolProperty; // edi

  v4 = (HTTP_LOG_FILE_CONFIG_CONTEXT *)operator new(0xE8u);
  v5 = (int *)v4;
  if ( v4 )
    HTTP_LOG_FILE_CONFIG_CONTEXT::HTTP_LOG_FILE_CONFIG_CONTEXT(v4);
  else
    v5 = 0;
  if ( v5 )
  {
    if ( a1 )
    {
      BoolProperty = Config_GetBoolProperty(a1, L"logInUTF8", v5 + 3);
      if ( BoolProperty >= 0 )
      {
        *a2 = (struct HTTP_LOG_FILE_CONFIG *)v5;
        return (unsigned int)BoolProperty;
      }
    }
    else
    {
      BoolProperty = -2147024809;
    }
    MULTISZ::~MULTISZ((MULTISZ *)(v5 + 40));
    STRU::~STRU((STRU *)(v5 + 26));
    STRU::~STRU((STRU *)(v5 + 12));
    operator delete(v5);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)BoolProperty;
}

```

## disassembly

```asm
0x180007338  mov     [rsp+arg_0], rbx
0x18000733d  mov     [rsp+arg_8], rsi
0x180007342  push    rdi
0x180007343  sub     rsp, 20h
0x180007347  mov     rsi, rdx
0x18000734a  mov     rdi, rcx
0x18000734d  mov     ecx, 0E8h; Size
0x180007352  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007357  mov     rbx, rax
0x18000735a  mov     [rsp+28h+arg_10], rax
0x18000735f  test    rax, rax
0x180007362  jz      short loc_18000736E
0x180007364  mov     rcx, rax; this
0x180007367  call    ??0HTTP_LOG_FILE_CONFIG_CONTEXT@@QEAA@XZ; HTTP_LOG_FILE_CONFIG_CONTEXT::HTTP_LOG_FILE_CONFIG_CONTEXT(void)
0x18000736c  jmp     short loc_180007370
0x18000736e  xor     ebx, ebx
0x180007370  test    rbx, rbx
0x180007373  jnz     short loc_18000737C
0x180007375  mov     edi, 8007000Eh
0x18000737a  jmp     short loc_1800073AF
0x18000737c  test    rdi, rdi
0x18000737f  jnz     short loc_1800073C1
0x180007381  mov     edi, 80070057h
0x180007386  lea     rcx, [rbx+0A0h]
0x18000738d  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180007393  lea     rcx, [rbx+68h]
0x180007397  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000739d  lea     rcx, [rbx+30h]
0x1800073a1  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800073a7  mov     rcx, rbx; Block
0x1800073aa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800073af  mov     eax, edi
0x1800073b1  mov     rbx, [rsp+28h+arg_0]
0x1800073b6  mov     rsi, [rsp+28h+arg_8]
0x1800073bb  add     rsp, 20h
0x1800073bf  pop     rdi
0x1800073c0  retn
0x1800073c1  lea     r8, [rbx+0Ch]; int *
0x1800073c5  lea     rdx, aLoginutf8; "logInUTF8"
0x1800073cc  mov     rcx, rdi; struct IAppHostElement *
0x1800073cf  call    ?Config_GetBoolProperty@@YAJPEAUIAppHostElement@@PEBGPEAH@Z; Config_GetBoolProperty(IAppHostElement *,ushort const *,int *)
0x1800073d4  mov     edi, eax
0x1800073d6  test    eax, eax
0x1800073d8  js      short loc_180007386
0x1800073da  mov     [rsi], rbx
0x1800073dd  jmp     short loc_1800073AF
```
