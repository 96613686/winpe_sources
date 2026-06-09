# TpmRegistry::QueryValue(ushort const *,ushort const *,ulong,void *,ulong,ulong *)

- ea: `0x140030218`
- end: `0x1400302e9`
- name: `?QueryValue@TpmRegistry@@SAJPEBG0KPEAXKPEAK@Z`
- size: `209`
- prototype: `static int(const unsigned __int16 *, const unsigned __int16 *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140022570`

## callees

- `0x14000a3d0`
- `0x140030150`
- `0x140030218`
- `0x140039780`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14003025e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003025e`

## pseudocode

```c
__int64 __fastcall TpmRegistry::QueryValue(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3,
        void *a4,
        unsigned int a5,
        unsigned int *a6)
{
  int v9; // ebx
  int v11; // [rsp+40h] [rbp-48h] BYREF
  struct WDFKEY__ *v12; // [rsp+48h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-38h] BYREF

  v12 = 0;
  v11 = 0;
  DestinationString = 0;
  v9 = TpmRegistry::OpenKey(a1, 0x20019u, &v12);
  if ( v9 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, a2);
    v9 = (*((__int64 (__fastcall **)(PKDPC, struct WDFKEY__ *, struct _UNICODE_STRING *, _QWORD, void *, unsigned int *, int *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
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
0x140030218  mov     rax, rsp
0x14003021b  push    rbx
0x14003021c  push    rbp
0x14003021d  push    rsi
0x14003021e  push    rdi
0x14003021f  sub     rsp, 68h
0x140030223  mov     esi, r8d
0x140030226  mov     qword ptr [rax-40h], 0
0x14003022e  mov     rbp, rdx
0x140030231  mov     dword ptr [rax-48h], 0
0x140030238  xorps   xmm0, xmm0
0x14003023b  lea     r8, [rax-40h]; struct WDFKEY__ **
0x14003023f  mov     edx, 20019h; unsigned int
0x140030244  mov     rdi, r9
0x140030247  movups  xmmword ptr [rax-38h], xmm0
0x14003024b  call    ?OpenKey@TpmRegistry@@CAJPEBGKPEAPEAUWDFKEY__@@@Z; TpmRegistry::OpenKey(ushort const *,ulong,WDFKEY__ * *)
0x140030250  mov     ebx, eax
0x140030252  test    eax, eax
0x140030254  js      short loc_1400302C4
0x140030256  mov     rdx, rbp; SourceString
0x140030259  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x14003025e  call    cs:__imp_RtlInitUnicodeString
0x140030265  nop     dword ptr [rax+rax+00h]
0x14003026a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140030271  lea     rcx, [rsp+88h+var_48]
0x140030276  mov     r9d, [rsp+88h+arg_20]
0x14003027e  lea     r8, [rsp+88h+DestinationString]
0x140030283  mov     rdx, [rsp+88h+var_40]
0x140030288  mov     [rsp+88h+var_58], rcx
0x14003028d  mov     rcx, [rsp+88h+arg_28]
0x140030295  mov     rax, [rax+758h]
0x14003029c  mov     [rsp+88h+var_60], rcx
0x1400302a1  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x1400302a8  mov     [rsp+88h+var_68], rdi
0x1400302ad  call    _guard_dispatch_icall
0x1400302b2  mov     ebx, eax
0x1400302b4  test    eax, eax
0x1400302b6  js      short loc_1400302C4
0x1400302b8  cmp     [rsp+88h+var_48], esi
0x1400302bc  mov     eax, 0C0000001h
0x1400302c1  cmovnz  ebx, eax
0x1400302c4  mov     rcx, [rsp+88h+var_40]; struct WDFKEY__ *
0x1400302c9  call    ?CloseKey@TpmRegistry@@CAXPEAUWDFKEY__@@@Z; TpmRegistry::CloseKey(WDFKEY__ *)
0x1400302ce  cmp     ebx, 80000005h
0x1400302d4  jnz     short loc_1400302DD
0x1400302d6  neg     rdi
0x1400302d9  sbb     eax, eax
0x1400302db  and     ebx, eax
0x1400302dd  mov     eax, ebx
0x1400302df  add     rsp, 68h
0x1400302e3  pop     rdi
0x1400302e4  pop     rsi
0x1400302e5  pop     rbp
0x1400302e6  pop     rbx
0x1400302e7  retn
```
