# CUwfConfiguration::CreateKey(HKEY__ *,ushort const *,ulong,ulong,ulong *,CUwfRegKey &)

- ea: `0x180006b20`
- end: `0x180006b9d`
- name: `?CreateKey@CUwfConfiguration@@QEAAJPEAUHKEY__@@PEBGKKPEAKAEAVCUwfRegKey@@@Z`
- size: `125`
- prototype: `__int64 __fastcall(CUwfConfiguration *this, HKEY, const unsigned __int16 *, REGSAM, DWORD, unsigned int *, HKEY *phkResult)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006a40`
- `0x180006c80`

## callees

- `0x180006b20`
- `0x18000d9f0`
- `0x18000db50`

## pseudocode

```c
__int64 __fastcall CUwfConfiguration::CreateKey(
        CUwfConfiguration *this,
        HKEY a2,
        const unsigned __int16 *a3,
        REGSAM a4,
        DWORD a5,
        unsigned int *a6,
        HKEY *phkResult)
{
  void *v7; // rax

  v7 = (void *)*((_QWORD *)this + 1);
  if ( v7 == (void *)-1LL )
    return CUwfRegKey::Create(phkResult, a2, a3, 0, a5, a4, 0, a6);
  else
    return CUwfRegKey::CreateTransacted(phkResult, a2, a3, 0, a5, a4, 0, a6, v7);
}

```

## disassembly

```asm
0x180006b20  mov     r11, rsp
0x180006b23  sub     rsp, 58h
0x180006b27  mov     rax, [rcx+8]
0x180006b2b  mov     rcx, [rsp+58h+phkResult]; phkResult
0x180006b33  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006b37  jz      short loc_180006B6A
0x180006b39  mov     [r11-18h], rax
0x180006b3d  mov     rax, [rsp+58h+arg_28]
0x180006b45  mov     [r11-20h], rax
0x180006b49  mov     eax, [rsp+58h+arg_20]
0x180006b50  mov     qword ptr [r11-28h], 0
0x180006b58  mov     [r11-30h], r9d
0x180006b5c  xor     r9d, r9d; lpClass
0x180006b5f  mov     [rsp+58h+var_38], eax; DWORD
0x180006b63  call    ?CreateTransacted@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAKPEAX@Z; CUwfRegKey::CreateTransacted(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *,void *)
0x180006b68  jmp     short loc_180006B98
0x180006b6a  mov     rax, [rsp+58h+arg_28]
0x180006b72  mov     [rsp+58h+var_20], rax; LPDWORD
0x180006b77  mov     eax, [rsp+58h+arg_20]
0x180006b7e  mov     [rsp+58h+var_28], 0; LPSECURITY_ATTRIBUTES
0x180006b87  mov     [rsp+58h+var_30], r9d; REGSAM
0x180006b8c  xor     r9d, r9d; lpClass
0x180006b8f  mov     [rsp+58h+var_38], eax; DWORD
0x180006b93  call    ?Create@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; CUwfRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180006b98  add     rsp, 58h
0x180006b9c  retn
```
