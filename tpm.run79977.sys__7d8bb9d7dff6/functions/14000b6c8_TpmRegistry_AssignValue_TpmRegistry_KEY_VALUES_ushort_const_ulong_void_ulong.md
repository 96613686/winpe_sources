# TpmRegistry::AssignValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong)

- ea: `0x14000b6c8`
- end: `0x14000b7a1`
- name: `?AssignValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXK@Z`
- size: `217`
- prototype: `static int __high(enum TpmRegistry::KEY_VALUES, const unsigned __int16 *, unsigned int, void *, unsigned int)`
- caller_count: `11`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140006300`
- `0x140006838`
- `0x14000b7a8`
- `0x140012568`
- `0x1400171d0`
- `0x140018a30`
- `0x140018fc8`
- `0x14001a5b8`
- `0x14001d4e4`
- `0x1400211dc`
- `0x14002f0b0`

## callees

- `0x14000a0a4`
- `0x14000a3d0`
- `0x14000b6c8`
- `0x14000c4e8`
- `0x140039780`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000b737`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b737`

## pseudocode

```c
__int64 __fastcall TpmRegistry::AssignValue(__int64 a1, const WCHAR *a2, unsigned int a3, __int64 a4, int a5)
{
  int v8; // edi
  int v9; // ebx
  int v10; // r8d
  struct WDFKEY__ *v12; // [rsp+40h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-40h] BYREF

  v12 = 0;
  DestinationString = 0;
  v8 = a1;
  v9 = TpmRegistry::OpenKey(a1, 131078, &v12);
  if ( v9 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, a2);
    v9 = (*((__int64 (__fastcall **)(PKDPC, struct WDFKEY__ *, struct _UNICODE_STRING *, _QWORD, int, __int64))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
          + 241))(
           WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
           v12,
           &DestinationString,
           a3,
           a5,
           a4);
  }
  TpmRegistry::CloseKey(v12);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_dSD(WPP_GLOBAL_Control->AttachedDevice, 30, v10, v8, (__int64)a2, v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000b6c8  push    rbx
0x14000b6ca  push    rbp
0x14000b6cb  push    rsi
0x14000b6cc  push    rdi
0x14000b6cd  push    r14
0x14000b6cf  sub     rsp, 60h
0x14000b6d3  mov     r14d, r8d
0x14000b6d6  mov     [rsp+88h+var_48], 0
0x14000b6df  mov     rsi, rdx
0x14000b6e2  lea     r8, [rsp+88h+var_48]
0x14000b6e7  xorps   xmm0, xmm0
0x14000b6ea  mov     edx, 20006h
0x14000b6ef  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x14000b6f4  mov     rbp, r9
0x14000b6f7  mov     edi, ecx
0x14000b6f9  call    ?OpenKey@TpmRegistry@@CAJW4KEY_VALUES@1@KPEAPEAUWDFKEY__@@@Z; TpmRegistry::OpenKey(TpmRegistry::KEY_VALUES,ulong,WDFKEY__ * *)
0x14000b6fe  mov     ebx, eax
0x14000b700  test    eax, eax
0x14000b702  jns     short loc_14000B72F
0x14000b704  mov     rcx, [rsp+88h+var_48]; struct WDFKEY__ *
0x14000b709  call    ?CloseKey@TpmRegistry@@CAXPEAUWDFKEY__@@@Z; TpmRegistry::CloseKey(WDFKEY__ *)
0x14000b70e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000b715  lea     rax, WPP_GLOBAL_Control
0x14000b71c  cmp     rcx, rax
0x14000b71f  jnz     short loc_14000B77E
0x14000b721  mov     eax, ebx
0x14000b723  add     rsp, 60h
0x14000b727  pop     r14
0x14000b729  pop     rdi
0x14000b72a  pop     rsi
0x14000b72b  pop     rbp
0x14000b72c  pop     rbx
0x14000b72d  retn
0x14000b72f  mov     rdx, rsi; SourceString
0x14000b732  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x14000b737  call    cs:__imp_RtlInitUnicodeString
0x14000b73e  nop     dword ptr [rax+rax+00h]
0x14000b743  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14000b74a  lea     r8, [rsp+88h+DestinationString]
0x14000b74f  mov     ecx, [rsp+88h+arg_20]
0x14000b756  mov     r9d, r14d
0x14000b759  mov     rdx, [rsp+88h+var_48]
0x14000b75e  mov     [rsp+88h+var_60], rbp
0x14000b763  mov     rax, [rax+788h]
0x14000b76a  mov     dword ptr [rsp+88h+var_68], ecx
0x14000b76e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14000b775  call    _guard_dispatch_icall
0x14000b77a  mov     ebx, eax
0x14000b77c  jmp     short loc_14000B704
0x14000b77e  mov     eax, [rcx+2Ch]
0x14000b781  test    al, 4
0x14000b783  jz      short loc_14000B721
0x14000b785  mov     rcx, [rcx+18h]
0x14000b789  mov     edx, 1Eh
0x14000b78e  mov     dword ptr [rsp+88h+var_60], ebx
0x14000b792  mov     r9d, edi
0x14000b795  mov     [rsp+88h+var_68], rsi
0x14000b79a  call    WPP_SF_dSD
0x14000b79f  jmp     short loc_14000B721
```
