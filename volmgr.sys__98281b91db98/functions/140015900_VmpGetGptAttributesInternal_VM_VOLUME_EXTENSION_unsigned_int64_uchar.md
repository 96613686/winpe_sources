# VmpGetGptAttributesInternal(VM_VOLUME_EXTENSION *,unsigned __int64 *,uchar *)

- ea: `0x140015900`
- end: `0x140015a62`
- name: `?VmpGetGptAttributesInternal@@YAJPEAVVM_VOLUME_EXTENSION@@PEA_KPEAE@Z`
- size: `354`
- prototype: `int(struct VM_VOLUME_EXTENSION *, unsigned __int64 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x140016ff0`

## callees

- `0x140002db0`
- `0x1400031b0`
- `0x140005050`
- `0x140005090`
- `0x140005120`
- `0x140005540`
- `0x140015900`
- `0x140015a70`

## pseudocode

```c
__int64 __fastcall VmpGetGptAttributesInternal(
        struct VM_VOLUME_EXTENSION *a1,
        unsigned __int64 *a2,
        unsigned __int8 *a3)
{
  NTSTATUS GptAttributes; // ebx
  _DWORD v8[36]; // [rsp+30h] [rbp-B8h] BYREF

  memset(v8, 0, sizeof(v8));
  *a2 = 0;
  *a3 = 1;
  if ( *((_BYTE *)a1 + 426) )
  {
    GptAttributes = 0;
    *a2 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(*((_QWORD *)a1 + 1) + 392LL) + 152LL))(*((_QWORD *)a1 + 54));
    return (unsigned int)GptAttributes;
  }
  GptAttributes = VmpSendDeviceControl(*((PDEVICE_OBJECT *)a1 + 43), 0x70048u, 0, 0, v8, 0x90u);
  if ( GptAttributes >= 0 )
  {
    if ( !SC_PART_ENTRY::IsRecognized((SC_PART_ENTRY *)v8) )
    {
      *a3 = 0;
      return (unsigned int)GptAttributes;
    }
    GptAttributes = VmpDiskGetGptAttributes(*((struct _DEVICE_OBJECT **)a1 + 43), a2);
    if ( GptAttributes < 0 )
      return (unsigned int)GptAttributes;
    if ( v8[0] )
    {
      if ( v8[0] != 1 )
        return (unsigned int)-1073741823;
      if ( !memcmp(&v8[8], &PARTITION_MSFT_RECOVERY_GUID, 0x10u) && !*(_BYTE *)(*((_QWORD *)a1 + 1) + 284LL) )
        goto LABEL_14;
    }
    else if ( LOBYTE(v8[8]) == 39 && !*(_BYTE *)(*((_QWORD *)a1 + 1) + 284LL) )
    {
LABEL_14:
      *a2 |= 0x8000000000000000uLL;
    }
  }
  return (unsigned int)GptAttributes;
}

```

## disassembly

```asm
0x140015900  mov     [rsp+arg_18], rbx
0x140015905  push    rsi
0x140015906  push    rdi
0x140015907  push    r14
0x140015909  sub     rsp, 0D0h
0x140015910  mov     rax, cs:__security_cookie
0x140015917  xor     rax, rsp
0x14001591a  mov     [rsp+0E8h+var_28], rax
0x140015922  mov     rsi, r8
0x140015925  mov     r14, rdx
0x140015928  mov     rdi, rcx
0x14001592b  xor     edx, edx; Val
0x14001592d  mov     r8d, 90h; Size
0x140015933  lea     rcx, [rsp+0E8h+var_B8]; void *
0x140015938  call    memset
0x14001593d  mov     qword ptr [r14], 0
0x140015944  mov     byte ptr [rsi], 1
0x140015947  cmp     byte ptr [rdi+1AAh], 0
0x14001594e  jnz     loc_140015A30
0x140015954  mov     rcx, [rdi+158h]; DeviceObject
0x14001595b  lea     rax, [rsp+0E8h+var_B8]
0x140015960  mov     [rsp+0E8h+var_C0], 90h; ULONG
0x140015968  xor     r9d, r9d; InputBufferLength
0x14001596b  xor     r8d, r8d; InputBuffer
0x14001596e  mov     [rsp+0E8h+var_C8], rax; PVOID
0x140015973  mov     edx, 70048h; IoControlCode
0x140015978  call    VmpSendDeviceControl
0x14001597d  mov     ebx, eax
0x14001597f  test    eax, eax
0x140015981  js      short loc_140015993
0x140015983  lea     rcx, [rsp+0E8h+var_B8]; this
0x140015988  call    ?IsRecognized@SC_PART_ENTRY@@QEAAEXZ; SC_PART_ENTRY::IsRecognized(void)
0x14001598d  test    al, al
0x14001598f  jnz     short loc_1400159BA
0x140015991  mov     [rsi], al
0x140015993  mov     eax, ebx
0x140015995  mov     rcx, [rsp+0E8h+var_28]
0x14001599d  xor     rcx, rsp; StackCookie
0x1400159a0  call    __security_check_cookie
0x1400159a5  mov     rbx, [rsp+0E8h+arg_18]
0x1400159ad  add     rsp, 0D0h
0x1400159b4  pop     r14
0x1400159b6  pop     rdi
0x1400159b7  pop     rsi
0x1400159b8  retn
0x1400159ba  mov     rcx, [rdi+158h]; struct _DEVICE_OBJECT *
0x1400159c1  mov     rdx, r14; unsigned __int64 *
0x1400159c4  call    ?VmpDiskGetGptAttributes@@YAJPEAU_DEVICE_OBJECT@@PEA_K@Z; VmpDiskGetGptAttributes(_DEVICE_OBJECT *,unsigned __int64 *)
0x1400159c9  mov     ebx, eax
0x1400159cb  test    eax, eax
0x1400159cd  js      short loc_140015993
0x1400159cf  mov     ecx, [rsp+0E8h+var_B8]
0x1400159d3  test    ecx, ecx
0x1400159d5  jz      short loc_140015A06
0x1400159d7  cmp     ecx, 1
0x1400159da  jnz     short loc_140015A58
0x1400159dc  mov     r8d, 10h; Size
0x1400159e2  lea     rdx, PARTITION_MSFT_RECOVERY_GUID; Buf2
0x1400159e9  lea     rcx, [rsp+0E8h+Buf1]; Buf1
0x1400159ee  call    memcmp
0x1400159f3  test    eax, eax
0x1400159f5  jnz     short loc_140015993
0x1400159f7  mov     rax, [rdi+8]
0x1400159fb  cmp     byte ptr [rax+11Ch], 0
0x140015a02  jnz     short loc_140015993
0x140015a04  jmp     short loc_140015A1E
0x140015a06  cmp     [rsp+0E8h+Buf1], 27h ; '''
0x140015a0b  jnz     short loc_140015993
0x140015a0d  mov     rax, [rdi+8]
0x140015a11  cmp     byte ptr [rax+11Ch], 0
0x140015a18  jnz     loc_140015993
0x140015a1e  mov     rax, 8000000000000000h
0x140015a28  or      [r14], rax
0x140015a2b  jmp     loc_140015993
0x140015a30  mov     rax, [rdi+8]
0x140015a34  xor     ebx, ebx
0x140015a36  mov     rcx, [rdi+1B0h]
0x140015a3d  mov     rdx, [rax+188h]
0x140015a44  mov     rax, [rdx+98h]
0x140015a4b  call    _guard_dispatch_icall
0x140015a50  mov     [r14], rax
0x140015a53  jmp     loc_140015993
0x140015a58  mov     ebx, 0C0000001h
0x140015a5d  jmp     loc_140015993
```
