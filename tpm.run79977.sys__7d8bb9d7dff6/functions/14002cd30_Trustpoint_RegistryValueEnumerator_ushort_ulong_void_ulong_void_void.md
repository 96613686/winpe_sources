# Trustpoint::_RegistryValueEnumerator(ushort *,ulong,void *,ulong,void *,void *)

- ea: `0x14002cd30`
- end: `0x14002cdd3`
- name: `?_RegistryValueEnumerator@Trustpoint@@SAJPEAGKPEAXK11@Z`
- size: `163`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned int@<edx>, void *@<r8>, unsigned int@<r9d>, void *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x14001a9d4`
- `0x140022050`
- `0x14002aaa0`
- `0x14002cd30`

## pseudocode

```c
__int64 __fastcall Trustpoint::_RegistryValueEnumerator(
        unsigned __int16 *a1,
        int a2,
        void *a3,
        unsigned int a4,
        void ***a5)
{
  void **v8; // rdi
  struct Trustpoint::_QUOTER *v9; // r11
  size_t pcbLength[7]; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v12; // [rsp+88h] [rbp+10h] BYREF

  v12 = 0;
  pcbLength[0] = 0;
  if ( a2 == 3 && a4 >= 4 )
  {
    v8 = *a5;
    v12 = *(_DWORD *)*a5 + *((_DWORD *)*a5 + 2) - *((_DWORD *)*a5 + 4);
    RtlStringCbLengthW(a1, v12, pcbLength);
    if ( !(unsigned int)Trustpoint::PerformTrustPointWithKey(v9, a3, a4, a1, pcbLength[0], v8[2], &v12) )
      BufferAccessor::Skip((BufferAccessor *)v8, v12);
  }
  return 0;
}

```

## disassembly

```asm
0x14002cd30  mov     rax, rsp
0x14002cd33  push    rbx
0x14002cd34  push    rbp
0x14002cd35  push    rsi
0x14002cd36  push    rdi
0x14002cd37  sub     rsp, 58h
0x14002cd3b  mov     dword ptr [rax+10h], 0
0x14002cd42  mov     ebx, r9d
0x14002cd45  mov     qword ptr [rax-38h], 0
0x14002cd4d  mov     rbp, r8
0x14002cd50  mov     rsi, rcx
0x14002cd53  cmp     edx, 3
0x14002cd56  jnz     short loc_14002CDC7
0x14002cd58  cmp     ebx, 4
0x14002cd5b  jb      short loc_14002CDC7
0x14002cd5d  mov     rax, [rsp+78h+arg_20]
0x14002cd65  lea     r8, [rsp+78h+pcbLength]; pcbLength
0x14002cd6a  mov     rdi, [rax]
0x14002cd6d  mov     r11, [rax+8]
0x14002cd71  mov     edx, [rdi+8]
0x14002cd74  sub     edx, [rdi+10h]
0x14002cd77  add     edx, [rdi]; cbMax
0x14002cd79  mov     [rsp+78h+arg_8], edx
0x14002cd80  call    RtlStringCbLengthW
0x14002cd85  mov     rax, [rdi+10h]
0x14002cd89  lea     r8, [rsp+78h+arg_8]
0x14002cd91  mov     [rsp+78h+var_48], r8; unsigned int *
0x14002cd96  mov     r9, rsi; unsigned __int16 *
0x14002cd99  mov     [rsp+78h+var_50], rax; void *
0x14002cd9e  mov     r8d, ebx; unsigned int
0x14002cda1  mov     eax, dword ptr [rsp+78h+pcbLength]
0x14002cda5  mov     rdx, rbp; void *
0x14002cda8  mov     rcx, r11; struct Trustpoint::_QUOTER *
0x14002cdab  mov     [rsp+78h+var_58], eax; unsigned int
0x14002cdaf  call    ?PerformTrustPointWithKey@Trustpoint@@CAJPEAU_QUOTER@1@PEAXIPEBGI1PEAI@Z; Trustpoint::PerformTrustPointWithKey(Trustpoint::_QUOTER *,void *,uint,ushort const *,uint,void *,uint *)
0x14002cdb4  test    eax, eax
0x14002cdb6  jnz     short loc_14002CDC7
0x14002cdb8  mov     edx, [rsp+78h+arg_8]; unsigned int
0x14002cdbf  mov     rcx, rdi; this
0x14002cdc2  call    ?Skip@BufferAccessor@@QEAAJI@Z; BufferAccessor::Skip(uint)
0x14002cdc7  xor     eax, eax
0x14002cdc9  add     rsp, 58h
0x14002cdcd  pop     rdi
0x14002cdce  pop     rsi
0x14002cdcf  pop     rbp
0x14002cdd0  pop     rbx
0x14002cdd1  retn
```
