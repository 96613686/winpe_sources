# TpmRegistry::AssignValue(ushort const *,ushort const *,ulong,void *,ulong)

- ea: `0x14002f7a4`
- end: `0x14002f875`
- name: `?AssignValue@TpmRegistry@@SAJPEBG0KPEAXK@Z`
- size: `209`
- prototype: `static int(const unsigned __int16 *, const unsigned __int16 *, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400222b8`

## callees

- `0x14000a3d0`
- `0x14002f7a4`
- `0x140030150`
- `0x1400302f0`
- `0x140039780`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14002f7e9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002f7e9`

## pseudocode

```c
__int64 __fastcall TpmRegistry::AssignValue(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        void *a4,
        unsigned int a5)
{
  int v8; // edi
  int v9; // ebx
  int v10; // edx
  int v11; // r8d
  struct WDFKEY__ *v13; // [rsp+40h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-40h] BYREF

  v13 = 0;
  DestinationString = 0;
  v8 = (int)a1;
  v9 = TpmRegistry::OpenKey(a1, 0x20006u, &v13);
  if ( v9 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, a2);
    v9 = (*((__int64 (__fastcall **)(PKDPC, struct WDFKEY__ *, struct _UNICODE_STRING *, _QWORD, unsigned int, void *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
          + 241))(
           WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
           v13,
           &DestinationString,
           a3,
           a5,
           a4);
  }
  TpmRegistry::CloseKey(v13);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_SSD(WPP_GLOBAL_Control->AttachedDevice, v10, v11, v8, (__int64)a2, v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14002f7a4  push    rbx
0x14002f7a6  push    rbp
0x14002f7a7  push    rsi
0x14002f7a8  push    rdi
0x14002f7a9  push    r14
0x14002f7ab  sub     rsp, 60h
0x14002f7af  mov     r14d, r8d
0x14002f7b2  mov     [rsp+88h+var_48], 0
0x14002f7bb  mov     rsi, rdx
0x14002f7be  lea     r8, [rsp+88h+var_48]; struct WDFKEY__ **
0x14002f7c3  xorps   xmm0, xmm0
0x14002f7c6  mov     edx, 20006h; unsigned int
0x14002f7cb  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x14002f7d0  mov     rbp, r9
0x14002f7d3  mov     rdi, rcx
0x14002f7d6  call    ?OpenKey@TpmRegistry@@CAJPEBGKPEAPEAUWDFKEY__@@@Z; TpmRegistry::OpenKey(ushort const *,ulong,WDFKEY__ * *)
0x14002f7db  mov     ebx, eax
0x14002f7dd  test    eax, eax
0x14002f7df  js      short loc_14002F82E
0x14002f7e1  mov     rdx, rsi; SourceString
0x14002f7e4  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x14002f7e9  call    cs:__imp_RtlInitUnicodeString
0x14002f7f0  nop     dword ptr [rax+rax+00h]
0x14002f7f5  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14002f7fc  lea     r8, [rsp+88h+DestinationString]
0x14002f801  mov     ecx, [rsp+88h+arg_20]
0x14002f808  mov     r9d, r14d
0x14002f80b  mov     rdx, [rsp+88h+var_48]
0x14002f810  mov     [rsp+88h+var_60], rbp
0x14002f815  mov     rax, [rax+788h]
0x14002f81c  mov     dword ptr [rsp+88h+var_68], ecx
0x14002f820  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14002f827  call    _guard_dispatch_icall
0x14002f82c  mov     ebx, eax
0x14002f82e  mov     rcx, [rsp+88h+var_48]; struct WDFKEY__ *
0x14002f833  call    ?CloseKey@TpmRegistry@@CAXPEAUWDFKEY__@@@Z; TpmRegistry::CloseKey(WDFKEY__ *)
0x14002f838  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f83f  lea     rax, WPP_GLOBAL_Control
0x14002f846  cmp     rcx, rax
0x14002f849  jz      short loc_14002F867
0x14002f84b  mov     eax, [rcx+2Ch]
0x14002f84e  test    al, 4
0x14002f850  jz      short loc_14002F867
0x14002f852  mov     rcx, [rcx+18h]
0x14002f856  mov     r9, rdi
0x14002f859  mov     dword ptr [rsp+88h+var_60], ebx
0x14002f85d  mov     [rsp+88h+var_68], rsi
0x14002f862  call    WPP_SF_SSD
0x14002f867  mov     eax, ebx
0x14002f869  add     rsp, 60h
0x14002f86d  pop     r14
0x14002f86f  pop     rdi
0x14002f870  pop     rsi
0x14002f871  pop     rbp
0x14002f872  pop     rbx
0x14002f873  retn
```
