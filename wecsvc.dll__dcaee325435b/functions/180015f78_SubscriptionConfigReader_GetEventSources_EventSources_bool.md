# SubscriptionConfigReader::GetEventSources(_EventSources &,bool)

- ea: `0x180015f78`
- end: `0x180016091`
- name: `?GetEventSources@SubscriptionConfigReader@@QEBA_NAEAU_EventSources@@_N@Z`
- size: `281`
- prototype: `char __fastcall(HKEY *this, struct _EventSources *, bool)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800052cc`
- `0x18001483c`
- `0x18001718c`

## callees

- `0x180003e6c`
- `0x180011c24`
- `0x180011d6c`
- `0x180011e68`
- `0x180011f40`
- `0x180015c30`
- `0x180015f78`
- `0x180019a20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015fb5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015fb5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall SubscriptionConfigReader::GetEventSources(HKEY *this, struct _EventSources *a2, bool a3)
{
  __int64 v7; // r8
  _BYTE v8[40]; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 *v9; // [rsp+58h] [rbp-20h]
  HKEY v10; // [rsp+80h] [rbp+8h] BYREF
  HKEY CurrentSubKey; // [rsp+98h] [rbp+20h] BYREF

  v10 = 0;
  if ( RegOpenKeyExW(this[2], L"EventSources", 0, 0x20019u, &v10) )
    return 0;
  RegistryKeyEnumerator::RegistryKeyEnumerator((RegistryKeyEnumerator *)v8, v10);
  while ( !RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v8) )
  {
    CurrentSubKey = RegistryKeyEnumerator::GetCurrentSubKey((RegistryKeyEnumerator *)v8, 0x20019u);
    SubscriptionConfigReader::GetEventSource((SubscriptionConfigReader *)this, CurrentSubKey, v9, a2, a3);
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&CurrentSubKey);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_ddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (__int64)(*((_QWORD *)a2 + 11) - *((_QWORD *)a2 + 10)) >> 5,
      v7,
      *((unsigned int *)a2 + 12),
      (__int64)(*((_QWORD *)a2 + 8) - *((_QWORD *)a2 + 7)) >> 5,
      (__int64)(*((_QWORD *)a2 + 11) - *((_QWORD *)a2 + 10)) >> 5);
  }
  RegistryKeyEnumerator::~RegistryKeyEnumerator((RegistryKeyEnumerator *)v8);
  return 1;
}

```

## disassembly

```asm
0x180015f78  mov     r11, rsp
0x180015f7b  mov     [r11+10h], rbx
0x180015f7f  mov     [r11+18h], rsi
0x180015f83  push    rdi
0x180015f84  sub     rsp, 70h
0x180015f88  mov     sil, r8b
0x180015f8b  mov     rbx, rdx
0x180015f8e  mov     rdi, rcx
0x180015f91  mov     qword ptr [r11+8], 0
0x180015f99  lea     rax, [r11+8]
0x180015f9d  mov     [r11-58h], rax
0x180015fa1  mov     r9d, 20019h; samDesired
0x180015fa7  xor     r8d, r8d; ulOptions
0x180015faa  lea     rdx, aEventsources; "EventSources"
0x180015fb1  mov     rcx, [rcx+10h]; hKey
0x180015fb5  call    cs:__imp_RegOpenKeyExW
0x180015fbb  test    eax, eax
0x180015fbd  jz      short loc_180015FC6
0x180015fbf  xor     al, al
0x180015fc1  jmp     loc_18001607F
0x180015fc6  mov     rdx, [rsp+78h+arg_0]; HKEY
0x180015fce  lea     rcx, [rsp+78h+var_48]; this
0x180015fd3  call    ??0RegistryKeyEnumerator@@QEAA@PEAUHKEY__@@@Z; RegistryKeyEnumerator::RegistryKeyEnumerator(HKEY__ *)
0x180015fd8  nop
0x180015fd9  jmp     short loc_180016018
0x180015fdb  mov     edx, 20019h; unsigned int
0x180015fe0  lea     rcx, [rsp+78h+var_48]; this
0x180015fe5  call    ?GetCurrentSubKey@RegistryKeyEnumerator@@QEBAPEAUHKEY__@@K@Z; RegistryKeyEnumerator::GetCurrentSubKey(ulong)
0x180015fea  mov     [rsp+78h+arg_18], rax
0x180015ff2  mov     [rsp+78h+var_58], sil; bool
0x180015ff7  mov     r9, rbx; struct _EventSources *
0x180015ffa  mov     r8, [rsp+78h+var_20]; unsigned __int16 *
0x180015fff  mov     rdx, rax; HKEY
0x180016002  mov     rcx, rdi; this
0x180016005  call    ?GetEventSource@SubscriptionConfigReader@@QEBA_NPEAUHKEY__@@PEBGAEAU_EventSources@@_N@Z; SubscriptionConfigReader::GetEventSource(HKEY__ *,ushort const *,_EventSources &,bool)
0x18001600a  nop
0x18001600b  lea     rcx, [rsp+78h+arg_18]; this
0x180016013  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180016018  lea     rcx, [rsp+78h+var_48]; this
0x18001601d  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x180016022  test    eax, eax
0x180016024  jz      short loc_180015FDB
0x180016026  lea     rax, WPP_GLOBAL_Control
0x18001602d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016034  cmp     rcx, rax
0x180016037  jz      short loc_180016073
0x180016039  test    byte ptr [rcx+1Ch], 40h
0x18001603d  jz      short loc_180016073
0x18001603f  cmp     byte ptr [rcx+19h], 5
0x180016043  jb      short loc_180016073
0x180016045  mov     rdx, [rbx+58h]
0x180016049  sub     rdx, [rbx+50h]
0x18001604d  sar     rdx, 5
0x180016051  mov     rax, [rbx+40h]
0x180016055  sub     rax, [rbx+38h]
0x180016059  sar     rax, 5
0x18001605d  mov     [rsp+78h+var_50], edx
0x180016061  mov     dword ptr [rsp+78h+var_58], eax
0x180016065  mov     r9d, [rbx+30h]
0x180016069  mov     rcx, [rcx+10h]
0x18001606d  call    WPP_SF_ddd
0x180016072  nop
0x180016073  lea     rcx, [rsp+78h+var_48]; this
0x180016078  call    ??1RegistryKeyEnumerator@@QEAA@XZ; RegistryKeyEnumerator::~RegistryKeyEnumerator(void)
0x18001607d  mov     al, 1
0x18001607f  lea     r11, [rsp+78h+var_8]
0x180016084  mov     rbx, [r11+18h]
0x180016088  mov     rsi, [r11+20h]
0x18001608c  mov     rsp, r11
0x18001608f  pop     rdi
0x180016090  retn
```
