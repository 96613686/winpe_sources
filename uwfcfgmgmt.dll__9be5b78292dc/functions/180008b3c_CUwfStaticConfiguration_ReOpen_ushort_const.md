# CUwfStaticConfiguration::ReOpen(ushort const *)

- ea: `0x180008b3c`
- end: `0x180008bee`
- name: `?ReOpen@CUwfStaticConfiguration@@AEAAJPEBG@Z`
- size: `178`
- prototype: `int __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180008730`
- `0x180008c00`

## callees

- `0x180006240`
- `0x180008b3c`
- `0x180008c30`
- `0x18000de30`
- `0x18000df60`

## pseudocode

```c
int __fastcall CUwfStaticConfiguration::ReOpen(HKEY *this, const unsigned __int16 *a2)
{
  HKEY v4; // rax
  REGSAM v5; // edi
  int result; // eax
  HKEY v7; // rax
  HKEY v8; // rdx
  CUwfStaticVolumeConfiguration *v9; // rcx

  CUwfStaticConfiguration::Close(this);
  v4 = this[4];
  v5 = *((_BYTE *)this + 9) != 0 ? 131097 : 131103;
  if ( *((_QWORD *)v4 + 1) == -1 )
    result = CUwfRegKey::Open(this + 2, HKEY_LOCAL_MACHINE, a2, v5);
  else
    result = CUwfRegKey::OpenTransacted(this + 2, HKEY_LOCAL_MACHINE, a2, v5, *((HANDLE *)v4 + 1));
  if ( result >= 0 )
  {
    v7 = this[4];
    v8 = this[2];
    if ( *((_QWORD *)v7 + 1) == -1 )
      result = CUwfRegKey::Open(this + 3, v8, L"Volumes", v5);
    else
      result = CUwfRegKey::OpenTransacted(this + 3, v8, L"Volumes", v5, *((HANDLE *)v7 + 1));
    if ( result >= 0 )
    {
      v9 = (CUwfStaticVolumeConfiguration *)this[5];
      if ( v9 )
        return CUwfStaticVolumeConfiguration::ReOpen(v9, this[3]);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008b3c  push    rbx
0x180008b3e  push    rbp
0x180008b3f  push    rsi
0x180008b40  push    rdi
0x180008b41  sub     rsp, 38h
0x180008b45  mov     rbp, rdx
0x180008b48  mov     rbx, rcx
0x180008b4b  call    ?Close@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::Close(void)
0x180008b50  mov     al, [rbx+9]
0x180008b53  lea     rsi, [rbx+10h]
0x180008b57  neg     al
0x180008b59  mov     r8, rbp; lpSubKey
0x180008b5c  mov     rax, [rbx+20h]
0x180008b60  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180008b67  sbb     edi, edi
0x180008b69  and     edi, 0FFFFFFFAh
0x180008b6c  add     edi, 2001Fh
0x180008b72  mov     rcx, [rax+8]
0x180008b76  mov     r9d, edi; samDesired
0x180008b79  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180008b7d  jz      short loc_180008B8E
0x180008b7f  mov     [rsp+58h+var_38], rcx; HANDLE
0x180008b84  mov     rcx, rsi; phkResult
0x180008b87  call    ?OpenTransacted@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGKPEAX@Z; CUwfRegKey::OpenTransacted(HKEY__ *,ushort const *,ulong,void *)
0x180008b8c  jmp     short loc_180008B96
0x180008b8e  mov     rcx, rsi; phkResult
0x180008b91  call    ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180008b96  test    eax, eax
0x180008b98  js      short loc_180008BE5
0x180008b9a  mov     rax, [rbx+20h]
0x180008b9e  lea     r8, aVolumes; "Volumes"
0x180008ba5  mov     rdx, [rsi]; hKey
0x180008ba8  mov     r9d, edi; samDesired
0x180008bab  lea     rsi, [rbx+18h]
0x180008baf  mov     rcx, [rax+8]
0x180008bb3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180008bb7  jz      short loc_180008BC8
0x180008bb9  mov     [rsp+58h+var_38], rcx; HANDLE
0x180008bbe  mov     rcx, rsi; phkResult
0x180008bc1  call    ?OpenTransacted@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGKPEAX@Z; CUwfRegKey::OpenTransacted(HKEY__ *,ushort const *,ulong,void *)
0x180008bc6  jmp     short loc_180008BD0
0x180008bc8  mov     rcx, rsi; phkResult
0x180008bcb  call    ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180008bd0  test    eax, eax
0x180008bd2  js      short loc_180008BE5
0x180008bd4  mov     rcx, [rbx+28h]; this
0x180008bd8  test    rcx, rcx
0x180008bdb  jz      short loc_180008BE5
0x180008bdd  mov     rdx, [rsi]; HKEY
0x180008be0  call    ?ReOpen@CUwfStaticVolumeConfiguration@@QEAAJPEAUHKEY__@@@Z; CUwfStaticVolumeConfiguration::ReOpen(HKEY__ *)
0x180008be5  add     rsp, 38h
0x180008be9  pop     rdi
0x180008bea  pop     rsi
0x180008beb  pop     rbp
0x180008bec  pop     rbx
0x180008bed  retn
```
