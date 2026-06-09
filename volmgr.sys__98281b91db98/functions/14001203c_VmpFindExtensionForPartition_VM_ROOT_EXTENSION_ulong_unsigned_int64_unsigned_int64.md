# VmpFindExtensionForPartition(VM_ROOT_EXTENSION *,ulong,unsigned __int64,unsigned __int64)

- ea: `0x14001203c`
- end: `0x1400120e9`
- name: `?VmpFindExtensionForPartition@@YAPEAVVM_VOLUME_EXTENSION@@PEAVVM_ROOT_EXTENSION@@K_K1@Z`
- size: `173`
- prototype: `struct VM_VOLUME_EXTENSION *__fastcall(struct VM_ROOT_EXTENSION *, unsigned int, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000fb20`

## callees

- `0x140002db0`
- `0x140005540`
- `0x14001203c`

## pseudocode

```c
struct VM_VOLUME_EXTENSION *__fastcall VmpFindExtensionForPartition(
        struct VM_ROOT_EXTENSION *a1,
        int a2,
        __int64 a3,
        __int64 a4)
{
  __int64 **v8; // rsi
  __int64 *i; // rdi
  struct _DEVICE_OBJECT *v10; // rcx
  _QWORD v12[25]; // [rsp+30h] [rbp-C8h] BYREF

  memset(v12, 0, 0x90u);
  v8 = (__int64 **)((char *)a1 + 208);
  for ( i = *v8; i != (__int64 *)v8; i = (__int64 *)*i )
  {
    if ( !*((_BYTE *)i + 394) )
    {
      v10 = (struct _DEVICE_OBJECT *)i[39];
      if ( v10 )
      {
        if ( *((_DWORD *)i + 88) == a2
          && VmpSendDeviceControl(v10, 0x70048u, 0, 0, v12, 0x90u) >= 0
          && v12[1] == a3
          && v12[2] == a4 )
        {
          return (struct VM_VOLUME_EXTENSION *)(i - 4);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14001203c  push    rbx
0x14001203e  push    rbp
0x14001203f  push    rsi
0x140012040  push    rdi
0x140012041  push    r14
0x140012043  push    r15
0x140012045  sub     rsp, 0C8h
0x14001204c  mov     r14, r8
0x14001204f  mov     r15d, edx
0x140012052  mov     rsi, rcx
0x140012055  xor     edx, edx; Val
0x140012057  mov     r8d, 90h; Size
0x14001205d  lea     rcx, [rsp+0F8h+var_C8]; void *
0x140012062  mov     rbp, r9
0x140012065  call    memset
0x14001206a  add     rsi, 0D0h
0x140012071  mov     rdi, [rsi]
0x140012074  cmp     rdi, rsi
0x140012077  jz      short loc_1400120D6
0x140012079  cmp     byte ptr [rdi+18Ah], 0
0x140012080  jnz     short loc_1400120CB
0x140012082  mov     rcx, [rdi+138h]; DeviceObject
0x140012089  test    rcx, rcx
0x14001208c  jz      short loc_1400120CB
0x14001208e  cmp     [rdi+160h], r15d
0x140012095  jnz     short loc_1400120CB
0x140012097  lea     rax, [rsp+0F8h+var_C8]
0x14001209c  mov     [rsp+0F8h+var_D0], 90h; ULONG
0x1400120a4  xor     r9d, r9d; InputBufferLength
0x1400120a7  mov     [rsp+0F8h+var_D8], rax; PVOID
0x1400120ac  xor     r8d, r8d; InputBuffer
0x1400120af  mov     edx, 70048h; IoControlCode
0x1400120b4  call    VmpSendDeviceControl
0x1400120b9  test    eax, eax
0x1400120bb  js      short loc_1400120CB
0x1400120bd  cmp     [rsp+0F8h+var_C0], r14
0x1400120c2  jnz     short loc_1400120CB
0x1400120c4  cmp     [rsp+0F8h+var_B8], rbp
0x1400120c9  jz      short loc_1400120D0
0x1400120cb  mov     rdi, [rdi]
0x1400120ce  jmp     short loc_140012074
0x1400120d0  lea     rax, [rdi-20h]
0x1400120d4  jmp     short loc_1400120D8
0x1400120d6  xor     eax, eax
0x1400120d8  add     rsp, 0C8h
0x1400120df  pop     r15
0x1400120e1  pop     r14
0x1400120e3  pop     rdi
0x1400120e4  pop     rsi
0x1400120e5  pop     rbp
0x1400120e6  pop     rbx
0x1400120e7  retn
```
