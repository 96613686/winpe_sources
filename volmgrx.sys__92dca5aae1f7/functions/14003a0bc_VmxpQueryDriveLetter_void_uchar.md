# VmxpQueryDriveLetter(void *,uchar *)

- ea: `0x14003a0bc`
- end: `0x14003a3b2`
- name: `?VmxpQueryDriveLetter@@YAJPEAXPEAE@Z`
- size: `758`
- prototype: `__int64 __fastcall(void *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x14004a88c`

## callees

- `0x14001b960`
- `0x14001b9a0`
- `0x14003a0bc`
- `0x14005d644`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14003a366`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a366`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003a1b7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003a1b7`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14003a1d4`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14003a1d4`
- `ntoskrnl!ExAllocatePool2` at `0x14003a152`
- `ntoskrnl!ExAllocatePool2` at `0x14003a233`
- `ntoskrnl!ExAllocatePool2` at `0x14003a152`
- `ntoskrnl!ExAllocatePool2` at `0x14003a233`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a351`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a37c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a351`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a37c`

## string_xrefs

- `0x14003a193`: `\Device\MountPointManager`

## pseudocode

```c
__int64 __fastcall VmxpQueryDriveLetter(void *a1, unsigned __int8 *a2)
{
  VMX_GLOBAL_DATA *v2; // r15
  __int64 (__fastcall *v4)(void *, unsigned __int16 *, _QWORD); // rax
  _QWORD *v6; // rsi
  NTSTATUS DeviceObjectPointer; // edi
  ULONG v8; // r14d
  __int64 Pool2; // rax
  ULONG v10; // r15d
  _DWORD *v11; // rax
  _DWORD *v12; // rbx
  unsigned int i; // edx
  int v14; // ecx
  __int64 v15; // r9
  unsigned __int16 v17; // [rsp+40h] [rbp-29h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+48h] [rbp-21h] BYREF
  PFILE_OBJECT FileObject; // [rsp+50h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-11h] BYREF
  ULONG v21[4]; // [rsp+68h] [rbp-1h] BYREF
  __int128 v22; // [rsp+78h] [rbp+Fh]

  v2 = Global;
  *a2 = 0;
  DeviceObject = 0;
  FileObject = 0;
  v4 = (__int64 (__fastcall *)(void *, unsigned __int16 *, _QWORD))*((_QWORD *)v2 + 17);
  v17 = 0;
  v6 = 0;
  DestinationString = 0;
  *(_OWORD *)v21 = 0;
  v22 = 0;
  DeviceObjectPointer = v4(a1, &v17, 0);
  if ( DeviceObjectPointer == -2147483643 )
  {
    v8 = v17 + 24;
    Pool2 = ExAllocatePool2(258, v8, 538996054);
    v6 = (_QWORD *)Pool2;
    if ( !Pool2 )
    {
LABEL_3:
      DeviceObjectPointer = -1073741670;
      goto LABEL_31;
    }
    DeviceObjectPointer = (*((__int64 (__fastcall **)(void *, unsigned __int16 *, __int64))v2 + 17))(
                            a1,
                            &v17,
                            Pool2 + 24);
    if ( DeviceObjectPointer >= 0 )
    {
      *(_OWORD *)v6 = 0;
      v6[2] = 0;
      *((_WORD *)v6 + 6) = v17;
      *((_DWORD *)v6 + 2) = 24;
      RtlInitUnicodeString(&DestinationString, L"\\Device\\MountPointManager");
      DeviceObjectPointer = IoGetDeviceObjectPointer(&DestinationString, 0x80u, &FileObject, &DeviceObject);
      if ( DeviceObjectPointer >= 0 )
      {
        DeviceObjectPointer = VmxpSendDeviceControl(DeviceObject, 0x6D0008u, v6, v8, v21, 0x20u, 0);
        if ( DeviceObjectPointer == -2147483643 )
        {
          v10 = v21[0];
          v11 = (_DWORD *)ExAllocatePool2(258, v21[0], 538996054);
          v12 = v11;
          if ( !v11 )
            goto LABEL_3;
          DeviceObjectPointer = VmxpSendDeviceControl(DeviceObject, 0x6D0008u, v6, v8, v11, v10, 0);
          if ( DeviceObjectPointer >= 0 )
          {
            for ( i = 0; i < v12[1]; ++i )
            {
              v14 = LOWORD(v12[6 * i + 3]);
              if ( (_WORD)v14 )
              {
                v15 = (unsigned int)v12[6 * i + 2];
                if ( (int)v15 + v14 > v10 )
                  break;
                if ( v14 == 28
                  && *(_WORD *)((char *)v12 + v15) == 92
                  && *(_WORD *)((char *)v12 + v15 + 2) == 68
                  && *(_WORD *)((char *)v12 + v15 + 4) == 111
                  && *(_WORD *)((char *)v12 + v15 + 6) == 115
                  && *(_WORD *)((char *)v12 + v15 + 8) == 68
                  && *(_WORD *)((char *)v12 + v15 + 10) == 101
                  && *(_WORD *)((char *)v12 + v15 + 12) == 118
                  && *(_WORD *)((char *)v12 + v15 + 14) == 105
                  && *(_WORD *)((char *)v12 + v15 + 16) == 99
                  && *(_WORD *)((char *)v12 + v15 + 18) == 101
                  && *(_WORD *)((char *)v12 + v15 + 20) == 115
                  && *(_WORD *)((char *)v12 + v15 + 22) == 92
                  && (unsigned __int16)(*(_WORD *)((char *)v12 + v15 + 24) - 65) <= 0x19u
                  && *(_WORD *)((char *)v12 + v15 + 26) == 58 )
                {
                  *a2 = *((_BYTE *)v12 + v15 + 24);
                  break;
                }
              }
            }
          }
          ExFreePoolWithTag(v12, 0);
        }
      }
    }
  }
LABEL_31:
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  return (unsigned int)DeviceObjectPointer;
}

```

## disassembly

```asm
0x14003a0bc  mov     [rsp-8+arg_10], rbx
0x14003a0c1  push    rbp
0x14003a0c2  push    rsi
0x14003a0c3  push    rdi
0x14003a0c4  push    r12
0x14003a0c6  push    r13
0x14003a0c8  push    r14
0x14003a0ca  push    r15
0x14003a0cc  lea     rbp, [rsp-27h]
0x14003a0d1  sub     rsp, 90h
0x14003a0d8  mov     rax, cs:__security_cookie
0x14003a0df  xor     rax, rsp
0x14003a0e2  mov     [rbp+57h+var_38], rax
0x14003a0e6  mov     r15, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14003a0ed  xor     r13d, r13d
0x14003a0f0  xorps   xmm1, xmm1
0x14003a0f3  mov     [rdx], r13b
0x14003a0f6  mov     r12, rdx
0x14003a0f9  mov     [rbp+57h+DeviceObject], r13
0x14003a0fd  xorps   xmm0, xmm0
0x14003a100  mov     [rbp+57h+FileObject], r13
0x14003a104  mov     rax, [r15+88h]
0x14003a10b  lea     rdx, [rbp+57h+var_80]
0x14003a10f  xor     r8d, r8d
0x14003a112  mov     [rbp+57h+var_80], r13w
0x14003a117  mov     rbx, rcx
0x14003a11a  mov     esi, r13d
0x14003a11d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14003a121  movups  xmmword ptr [rbp+57h+var_58], xmm1
0x14003a125  movups  [rbp+57h+var_48], xmm1
0x14003a129  call    _guard_dispatch_icall
0x14003a12e  mov     edi, eax
0x14003a130  cmp     eax, 80000005h
0x14003a135  jnz     loc_14003A35D
0x14003a13b  movzx   r14d, [rbp+57h+var_80]
0x14003a140  mov     ecx, 102h
0x14003a145  add     r14d, 18h
0x14003a149  mov     r8d, 20206D56h
0x14003a14f  mov     edx, r14d
0x14003a152  call    cs:__imp_ExAllocatePool2
0x14003a159  nop     dword ptr [rax+rax+00h]
0x14003a15e  mov     rsi, rax
0x14003a161  test    rax, rax
0x14003a164  jnz     short loc_14003A170
0x14003a166  mov     edi, 0C000009Ah
0x14003a16b  jmp     loc_14003A35D
0x14003a170  lea     r8, [rax+18h]
0x14003a174  mov     rcx, rbx
0x14003a177  mov     rax, [r15+88h]
0x14003a17e  lea     rdx, [rbp+57h+var_80]
0x14003a182  call    _guard_dispatch_icall
0x14003a187  mov     edi, eax
0x14003a189  test    eax, eax
0x14003a18b  js      loc_14003A35D
0x14003a191  xor     eax, eax
0x14003a193  lea     rdx, aDeviceMountpoi; "\\Device\\MountPointManager"
0x14003a19a  xorps   xmm0, xmm0
0x14003a19d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14003a1a1  movups  xmmword ptr [rsi], xmm0
0x14003a1a4  mov     [rsi+10h], rax
0x14003a1a8  movzx   eax, [rbp+57h+var_80]
0x14003a1ac  mov     [rsi+0Ch], ax
0x14003a1b0  mov     dword ptr [rsi+8], 18h
0x14003a1b7  call    cs:__imp_RtlInitUnicodeString
0x14003a1be  nop     dword ptr [rax+rax+00h]
0x14003a1c3  lea     r9, [rbp+57h+DeviceObject]; DeviceObject
0x14003a1c7  mov     edx, 80h; DesiredAccess
0x14003a1cc  lea     r8, [rbp+57h+FileObject]; FileObject
0x14003a1d0  lea     rcx, [rbp+57h+DestinationString]; ObjectName
0x14003a1d4  call    cs:__imp_IoGetDeviceObjectPointer
0x14003a1db  nop     dword ptr [rax+rax+00h]
0x14003a1e0  mov     edi, eax
0x14003a1e2  test    eax, eax
0x14003a1e4  js      loc_14003A35D
0x14003a1ea  mov     rcx, [rbp+57h+DeviceObject]; DeviceObject
0x14003a1ee  lea     rax, [rbp+57h+var_58]
0x14003a1f2  mov     [rsp+0C0h+var_90], r13b; BOOLEAN
0x14003a1f7  mov     r9d, r14d; InputBufferLength
0x14003a1fa  mov     [rsp+0C0h+var_98], 20h ; ' '; ULONG
0x14003a202  mov     r8, rsi; InputBuffer
0x14003a205  mov     edx, 6D0008h; IoControlCode
0x14003a20a  mov     [rsp+0C0h+var_A0], rax; PVOID
0x14003a20f  call    ?VmxpSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; VmxpSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x14003a214  mov     edi, eax
0x14003a216  cmp     eax, 80000005h
0x14003a21b  jnz     loc_14003A35D
0x14003a221  mov     r15d, [rbp+57h+var_58]
0x14003a225  mov     ecx, 102h
0x14003a22a  mov     edx, r15d
0x14003a22d  mov     r8d, 20206D56h
0x14003a233  call    cs:__imp_ExAllocatePool2
0x14003a23a  nop     dword ptr [rax+rax+00h]
0x14003a23f  mov     rbx, rax
0x14003a242  test    rax, rax
0x14003a245  jz      loc_14003A166
0x14003a24b  mov     rcx, [rbp+57h+DeviceObject]; DeviceObject
0x14003a24f  mov     r9d, r14d; InputBufferLength
0x14003a252  mov     [rsp+0C0h+var_90], r13b; BOOLEAN
0x14003a257  mov     r8, rsi; InputBuffer
0x14003a25a  mov     [rsp+0C0h+var_98], r15d; ULONG
0x14003a25f  mov     edx, 6D0008h; IoControlCode
0x14003a264  mov     [rsp+0C0h+var_A0], rax; PVOID
0x14003a269  call    ?VmxpSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; VmxpSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x14003a26e  mov     edi, eax
0x14003a270  test    eax, eax
0x14003a272  js      loc_14003A34C
0x14003a278  mov     r10d, [rbx+4]
0x14003a27c  mov     edx, r13d
0x14003a27f  cmp     edx, r10d
0x14003a282  jnb     loc_14003A34C
0x14003a288  mov     eax, edx
0x14003a28a  lea     r8, [rax+rax*2]
0x14003a28e  movzx   ecx, word ptr [rbx+r8*8+0Ch]
0x14003a294  test    cx, cx
0x14003a297  jz      loc_14003A33C
0x14003a29d  mov     r9d, [rbx+r8*8+8]
0x14003a2a2  lea     eax, [r9+rcx]
0x14003a2a6  cmp     eax, r15d
0x14003a2a9  ja      loc_14003A34C
0x14003a2af  cmp     ecx, 1Ch
0x14003a2b2  jnz     loc_14003A33C
0x14003a2b8  cmp     word ptr [r9+rbx], 5Ch ; '\'
0x14003a2be  jnz     short loc_14003A33C
0x14003a2c0  cmp     word ptr [r9+rbx+2], 44h ; 'D'
0x14003a2c7  jnz     short loc_14003A33C
0x14003a2c9  cmp     word ptr [r9+rbx+4], 6Fh ; 'o'
0x14003a2d0  jnz     short loc_14003A33C
0x14003a2d2  cmp     word ptr [r9+rbx+6], 73h ; 's'
0x14003a2d9  jnz     short loc_14003A33C
0x14003a2db  cmp     word ptr [r9+rbx+8], 44h ; 'D'
0x14003a2e2  jnz     short loc_14003A33C
0x14003a2e4  cmp     word ptr [r9+rbx+0Ah], 65h ; 'e'
0x14003a2eb  jnz     short loc_14003A33C
0x14003a2ed  cmp     word ptr [r9+rbx+0Ch], 76h ; 'v'
0x14003a2f4  jnz     short loc_14003A33C
0x14003a2f6  cmp     word ptr [r9+rbx+0Eh], 69h ; 'i'
0x14003a2fd  jnz     short loc_14003A33C
0x14003a2ff  cmp     word ptr [r9+rbx+10h], 63h ; 'c'
0x14003a306  jnz     short loc_14003A33C
0x14003a308  cmp     word ptr [r9+rbx+12h], 65h ; 'e'
0x14003a30f  jnz     short loc_14003A33C
0x14003a311  cmp     word ptr [r9+rbx+14h], 73h ; 's'
0x14003a318  jnz     short loc_14003A33C
0x14003a31a  cmp     word ptr [r9+rbx+16h], 5Ch ; '\'
0x14003a321  jnz     short loc_14003A33C
0x14003a323  movzx   eax, word ptr [r9+rbx+18h]
0x14003a329  sub     ax, 41h ; 'A'
0x14003a32d  cmp     ax, 19h
0x14003a331  ja      short loc_14003A33C
0x14003a333  cmp     word ptr [r9+rbx+1Ah], 3Ah ; ':'
0x14003a33a  jz      short loc_14003A343
0x14003a33c  inc     edx
0x14003a33e  jmp     loc_14003A27F
0x14003a343  mov     al, [r9+rbx+18h]
0x14003a348  mov     [r12], al
0x14003a34c  xor     edx, edx; Tag
0x14003a34e  mov     rcx, rbx; P
0x14003a351  call    cs:__imp_ExFreePoolWithTag
0x14003a358  nop     dword ptr [rax+rax+00h]
0x14003a35d  mov     rcx, [rbp+57h+FileObject]; Object
0x14003a361  test    rcx, rcx
0x14003a364  jz      short loc_14003A372
0x14003a366  call    cs:__imp_ObfDereferenceObject
0x14003a36d  nop     dword ptr [rax+rax+00h]
0x14003a372  test    rsi, rsi
0x14003a375  jz      short loc_14003A388
0x14003a377  xor     edx, edx; Tag
0x14003a379  mov     rcx, rsi; P
0x14003a37c  call    cs:__imp_ExFreePoolWithTag
0x14003a383  nop     dword ptr [rax+rax+00h]
0x14003a388  mov     eax, edi
0x14003a38a  mov     rcx, [rbp+57h+var_38]
0x14003a38e  xor     rcx, rsp; StackCookie
0x14003a391  call    __security_check_cookie
0x14003a396  mov     rbx, [rsp+0C0h+arg_10]
0x14003a39e  add     rsp, 90h
0x14003a3a5  pop     r15
0x14003a3a7  pop     r14
0x14003a3a9  pop     r13
0x14003a3ab  pop     r12
0x14003a3ad  pop     rdi
0x14003a3ae  pop     rsi
0x14003a3af  pop     rbp
0x14003a3b0  retn
```
