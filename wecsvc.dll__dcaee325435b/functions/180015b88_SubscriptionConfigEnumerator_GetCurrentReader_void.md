# SubscriptionConfigEnumerator::GetCurrentReader(void)

- ea: `0x180015b88`
- end: `0x180015c27`
- name: `?GetCurrentReader@SubscriptionConfigEnumerator@@QEAA?AV?$AutoRef@VSubscriptionConfigReader@@@wmi@@XZ`
- size: `159`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005ad0`

## callees

- `0x180003430`
- `0x18000526c`
- `0x180011e68`
- `0x180015b88`

## pseudocode

```c
_QWORD *__fastcall SubscriptionConfigEnumerator::GetCurrentReader(__int64 a1, _QWORD *a2)
{
  LPVOID v4; // rbx
  HKEY CurrentSubKey; // rax

  *a2 = 0;
  v4 = operator new(0x18u);
  if ( v4 )
  {
    CurrentSubKey = RegistryKeyEnumerator::GetCurrentSubKey((RegistryKeyEnumerator *)(a1 + 16), 0x20019u);
    *(_QWORD *)v4 = &wmi::RefBase::`vftable';
    *((_DWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 2) = CurrentSubKey;
    *(_QWORD *)v4 = &SubscriptionGlobalsReader::`vftable';
  }
  else
  {
    v4 = 0;
  }
  if ( v4 )
    _InterlockedIncrement((volatile signed __int32 *)v4 + 2);
  wmi::AutoRef<AbstractEventProcessor>::Release(a2);
  *a2 = v4;
  return a2;
}

```

## disassembly

```asm
0x180015b88  mov     rax, rsp
0x180015b8b  mov     [rax+8], rbx
0x180015b8f  mov     [rax+20h], rsi
0x180015b93  mov     [rax+10h], rdx
0x180015b97  push    rdi
0x180015b98  sub     rsp, 30h
0x180015b9c  mov     rdi, rdx
0x180015b9f  mov     rsi, rcx
0x180015ba2  mov     dword ptr [rax-18h], 0
0x180015ba9  mov     qword ptr [rdx], 0
0x180015bb0  mov     dword ptr [rax-18h], 1
0x180015bb7  mov     ecx, 18h; dwBytes
0x180015bbc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015bc1  mov     rbx, rax
0x180015bc4  mov     [rsp+38h+arg_10], rax
0x180015bc9  test    rax, rax
0x180015bcc  jz      short loc_180015BFD
0x180015bce  lea     rcx, [rsi+10h]; this
0x180015bd2  mov     edx, 20019h; unsigned int
0x180015bd7  call    ?GetCurrentSubKey@RegistryKeyEnumerator@@QEBAPEAUHKEY__@@K@Z; RegistryKeyEnumerator::GetCurrentSubKey(ulong)
0x180015bdc  lea     rcx, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x180015be3  mov     [rbx], rcx
0x180015be6  mov     dword ptr [rbx+8], 0
0x180015bed  mov     [rbx+10h], rax
0x180015bf1  lea     rax, ??_7SubscriptionGlobalsReader@@6B@; const SubscriptionGlobalsReader::`vftable'
0x180015bf8  mov     [rbx], rax
0x180015bfb  jmp     short loc_180015BFF
0x180015bfd  xor     ebx, ebx
0x180015bff  test    rbx, rbx
0x180015c02  jz      short loc_180015C08
0x180015c04  lock inc dword ptr [rbx+8]
0x180015c08  mov     rcx, rdi
0x180015c0b  call    ?Release@?$AutoRef@VAbstractEventProcessor@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractEventProcessor>::Release(void)
0x180015c10  mov     [rdi], rbx
0x180015c13  mov     rax, rdi
0x180015c16  mov     rbx, [rsp+38h+arg_0]
0x180015c1b  mov     rsi, [rsp+38h+arg_18]
0x180015c20  add     rsp, 30h
0x180015c24  pop     rdi
0x180015c25  retn
```
