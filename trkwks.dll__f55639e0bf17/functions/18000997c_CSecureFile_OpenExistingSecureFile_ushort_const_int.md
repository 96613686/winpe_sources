# CSecureFile::OpenExistingSecureFile(ushort const *,int)

- ea: `0x18000997c`
- end: `0x1800099e3`
- name: `?OpenExistingSecureFile@CSecureFile@@QEAAJPEBGH@Z`
- size: `103`
- prototype: `__int64 __fastcall(CSecureFile *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180009720`

## callees

- `0x18000997c`
- `0x180009ba4`

## pseudocode

```c
__int64 __fastcall CSecureFile::OpenExistingSecureFile(CSecureFile *this, const unsigned __int16 *a2, int a3)
{
  __int64 result; // rax

  _InterlockedAdd((volatile signed __int32 *)this + 2, 1u);
  result = TrkCreateFile(a2, a3 != 0 ? 1179785 : 1245599, 0x80u, 1u, 1u, 0, 0, (void **)this);
  if ( (int)result < 0 )
    *(_QWORD *)this = 0;
  _InterlockedDecrement((volatile signed __int32 *)this + 2);
  return result;
}

```

## disassembly

```asm
0x18000997c  mov     r11, rsp
0x18000997f  mov     [r11+8], rcx
0x180009983  push    rbx
0x180009984  sub     rsp, 40h
0x180009988  mov     rax, rdx
0x18000998b  mov     rbx, rcx
0x18000998e  mov     r9d, 1; unsigned int
0x180009994  lock add [rcx+8], r9d
0x180009999  neg     r8d
0x18000999c  sbb     edx, edx
0x18000999e  and     edx, 0FFFEFEEAh
0x1800099a4  add     edx, 13019Fh; unsigned int
0x1800099aa  mov     [r11-10h], rcx
0x1800099ae  mov     qword ptr [r11-18h], 0
0x1800099b6  mov     [rsp+48h+var_20], 0; unsigned int
0x1800099be  mov     [r11-28h], r9d
0x1800099c2  lea     r8d, [r9+7Fh]; unsigned int
0x1800099c6  mov     rcx, rax; unsigned __int16 *
0x1800099c9  call    ?TrkCreateFile@@YAJPEBGKKKKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAX@Z; TrkCreateFile(ushort const *,ulong,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void * *)
0x1800099ce  test    eax, eax
0x1800099d0  jns     short loc_1800099D9
0x1800099d2  mov     qword ptr [rbx], 0
0x1800099d9  lock dec dword ptr [rbx+8]
0x1800099dd  add     rsp, 40h
0x1800099e1  pop     rbx
0x1800099e2  retn
0x180011688  push    rbp
0x18001168a  sub     rsp, 40h
0x18001168e  mov     rbp, rdx
0x180011691  mov     rax, [rbp+50h]
0x180011695  lock dec dword ptr [rax+8]
0x180011699  add     rsp, 40h
0x18001169d  pop     rbp
0x18001169e  retn
```
