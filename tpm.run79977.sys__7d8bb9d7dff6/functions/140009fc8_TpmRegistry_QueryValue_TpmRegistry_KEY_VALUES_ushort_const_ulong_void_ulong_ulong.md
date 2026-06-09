# TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)

- ea: `0x140009fc8`
- end: `0x14000a09d`
- name: `?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z`
- size: `213`
- prototype: `static int __high(enum TpmRegistry::KEY_VALUES, const unsigned __int16 *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `21`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140005728`
- `0x140006838`
- `0x140009db0`
- `0x140009f70`
- `0x14000a4f0`
- `0x14000b0a8`
- `0x14000b7a8`
- `0x140012568`
- `0x1400171d0`
- `0x140018a30`
- `0x140018fc8`
- `0x14001a5b8`
- `0x14001a88c`
- `0x14001e394`
- `0x140022a90`
- `0x140022d00`
- `0x14002d050`
- `0x14002d8b4`
- `0x14002df64`
- `0x14002e118`
- `0x14002e300`

## callees

- `0x140009fc8`
- `0x14000a0a4`
- `0x14000a3d0`
- `0x140039780`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000a00e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a00e`

## pseudocode

```c
__int64 __fastcall TpmRegistry::QueryValue(
        __int64 a1,
        const WCHAR *a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6)
{
  int v9; // ebx
  int v11; // [rsp+40h] [rbp-48h] BYREF
  struct WDFKEY__ *v12; // [rsp+48h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-38h] BYREF

  v12 = 0;
  v11 = 0;
  DestinationString = 0;
  v9 = TpmRegistry::OpenKey(a1, 131097, &v12);
  if ( v9 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, a2);
    v9 = (*((__int64 (__fastcall **)(PKDPC, struct WDFKEY__ *, struct _UNICODE_STRING *, _QWORD, __int64, __int64, int *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
          + 235))(
           WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
           v12,
           &DestinationString,
           a5,
           a4,
           a6,
           &v11);
    if ( v9 >= 0 && v11 != a3 )
      v9 = -1073741823;
  }
  TpmRegistry::CloseKey(v12);
  if ( v9 == -2147483643 )
    return a4 != 0 ? 0x80000005 : 0;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140009fc8  mov     rax, rsp
0x140009fcb  push    rbx
0x140009fcc  push    rbp
0x140009fcd  push    rsi
0x140009fce  push    rdi
0x140009fcf  sub     rsp, 68h
0x140009fd3  mov     esi, r8d
0x140009fd6  mov     qword ptr [rax-40h], 0
0x140009fde  mov     rbp, rdx
0x140009fe1  mov     dword ptr [rax-48h], 0
0x140009fe8  xorps   xmm0, xmm0
0x140009feb  lea     r8, [rax-40h]
0x140009fef  mov     edx, 20019h
0x140009ff4  mov     rdi, r9
0x140009ff7  movups  xmmword ptr [rax-38h], xmm0
0x140009ffb  call    ?OpenKey@TpmRegistry@@CAJW4KEY_VALUES@1@KPEAPEAUWDFKEY__@@@Z; TpmRegistry::OpenKey(TpmRegistry::KEY_VALUES,ulong,WDFKEY__ * *)
0x14000a000  mov     ebx, eax
0x14000a002  test    eax, eax
0x14000a004  js      short loc_14000A068
0x14000a006  mov     rdx, rbp; SourceString
0x14000a009  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x14000a00e  call    cs:__imp_RtlInitUnicodeString
0x14000a015  nop     dword ptr [rax+rax+00h]
0x14000a01a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14000a021  lea     rcx, [rsp+88h+var_48]
0x14000a026  mov     r9d, [rsp+88h+arg_20]
0x14000a02e  lea     r8, [rsp+88h+DestinationString]
0x14000a033  mov     rdx, [rsp+88h+var_40]
0x14000a038  mov     [rsp+88h+var_58], rcx
0x14000a03d  mov     rcx, [rsp+88h+arg_28]
0x14000a045  mov     rax, [rax+758h]
0x14000a04c  mov     [rsp+88h+var_60], rcx
0x14000a051  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14000a058  mov     [rsp+88h+var_68], rdi
0x14000a05d  call    _guard_dispatch_icall
0x14000a062  mov     ebx, eax
0x14000a064  test    eax, eax
0x14000a066  jns     short loc_14000A086
0x14000a068  mov     rcx, [rsp+88h+var_40]; struct WDFKEY__ *
0x14000a06d  call    ?CloseKey@TpmRegistry@@CAXPEAUWDFKEY__@@@Z; TpmRegistry::CloseKey(WDFKEY__ *)
0x14000a072  cmp     ebx, 80000005h
0x14000a078  jz      short loc_14000A094
0x14000a07a  mov     eax, ebx
0x14000a07c  add     rsp, 68h
0x14000a080  pop     rdi
0x14000a081  pop     rsi
0x14000a082  pop     rbp
0x14000a083  pop     rbx
0x14000a084  retn
0x14000a086  cmp     [rsp+88h+var_48], esi
0x14000a08a  mov     eax, 0C0000001h
0x14000a08f  cmovnz  ebx, eax
0x14000a092  jmp     short loc_14000A068
0x14000a094  neg     rdi
0x14000a097  sbb     eax, eax
0x14000a099  and     ebx, eax
0x14000a09b  jmp     short loc_14000A07A
```
