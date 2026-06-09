# VmpQueryDeviceId(VM_VOLUME_EXTENSION *,ushort * *)

- ea: `0x14000e6dc`
- end: `0x14000e882`
- name: `?VmpQueryDeviceId@@YAJPEAVVM_VOLUME_EXTENSION@@PEAPEAG@Z`
- size: `422`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140015f70`

## callees

- `0x140005050`
- `0x140005120`
- `0x140005240`
- `0x14000e6dc`

## import_xrefs

- `ntoskrnl!IoGetDevicePropertyData` at `0x14000e7ac`
- `ntoskrnl!IoGetDevicePropertyData` at `0x14000e7ac`
- `ntoskrnl!KeReleaseMutex` at `0x14000e851`
- `ntoskrnl!KeReleaseMutex` at `0x14000e851`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e73a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e73a`
- `ntoskrnl!ExAllocatePool2` at `0x14000e817`
- `ntoskrnl!ExAllocatePool2` at `0x14000e817`

## pseudocode

```c
__int64 __fastcall VmpQueryDeviceId(struct VM_VOLUME_EXTENSION *a1, unsigned __int16 **a2)
{
  struct _KMUTANT *v2; // rbp
  NTSTATUS DevicePropertyData; // edi
  const wchar_t *v6; // rsi
  size_t v7; // rbx
  unsigned __int16 *Pool2; // rax
  ULONG Type; // [rsp+40h] [rbp-38h] BYREF
  ULONG RequiredSize; // [rsp+44h] [rbp-34h] BYREF
  __int128 Buf1; // [rsp+48h] [rbp-30h] BYREF

  v2 = (struct _KMUTANT *)((char *)a1 + 56);
  *a2 = 0;
  RequiredSize = 0;
  Type = 0;
  Buf1 = 0;
  KeWaitForSingleObject((char *)a1 + 56, Executive, 0, 0, 0);
  if ( *((_BYTE *)a1 + 426) )
  {
    if ( *((_QWORD *)a1 + 54) )
    {
      DevicePropertyData = 0;
      goto LABEL_7;
    }
LABEL_5:
    DevicePropertyData = -1073741810;
    goto LABEL_16;
  }
  if ( !*((_QWORD *)a1 + 43) )
    goto LABEL_5;
  DevicePropertyData = IoGetDevicePropertyData(
                         *((PDEVICE_OBJECT *)a1 + 45),
                         &DEVPKEY_Device_ClassGuid,
                         0,
                         0,
                         0x10u,
                         &Buf1,
                         &RequiredSize,
                         &Type);
  if ( DevicePropertyData < 0 )
    goto LABEL_16;
LABEL_7:
  if ( !memcmp(&Buf1, &GUID_DEVCLASS_SMRDISK, 0x10u) )
  {
    v6 = L"SMR\\Volume";
LABEL_11:
    v7 = 22;
    goto LABEL_13;
  }
  if ( _bittest64((const signed __int64 *)a1 + 39, 0x3Au) )
  {
    v6 = L"SCM\\Volume";
    goto LABEL_11;
  }
  v6 = L"STORAGE\\Volume";
  v7 = 30;
LABEL_13:
  Pool2 = (unsigned __int16 *)ExAllocatePool2(258, v7 + 2, 538987862);
  *a2 = Pool2;
  if ( Pool2 )
  {
    memmove(Pool2, v6, v7);
    (*a2)[v7 >> 1] = 0;
  }
  else
  {
    DevicePropertyData = -1073741670;
  }
LABEL_16:
  KeReleaseMutex(v2, 0);
  return (unsigned int)DevicePropertyData;
}

```

## disassembly

```asm
0x14000e6dc  mov     [rsp+arg_10], rbx
0x14000e6e1  mov     [rsp+arg_18], rbp
0x14000e6e6  push    rsi
0x14000e6e7  push    rdi
0x14000e6e8  push    r14
0x14000e6ea  sub     rsp, 60h
0x14000e6ee  mov     rax, cs:__security_cookie
0x14000e6f5  xor     rax, rsp
0x14000e6f8  mov     [rsp+78h+var_20], rax
0x14000e6fd  lea     rbp, [rcx+38h]
0x14000e701  mov     qword ptr [rdx], 0
0x14000e708  mov     r14, rdx
0x14000e70b  mov     [rsp+78h+var_34], 0
0x14000e713  mov     rbx, rcx
0x14000e716  mov     [rsp+78h+var_38], 0
0x14000e71e  xorps   xmm0, xmm0
0x14000e721  mov     [rsp+78h+Timeout], 0; Timeout
0x14000e72a  mov     rcx, rbp; Object
0x14000e72d  xor     r9d, r9d; Alertable
0x14000e730  xor     r8d, r8d; WaitMode
0x14000e733  xor     edx, edx; WaitReason
0x14000e735  movups  [rsp+78h+Buf1], xmm0
0x14000e73a  call    cs:__imp_KeWaitForSingleObject
0x14000e741  nop     dword ptr [rax+rax+00h]
0x14000e746  cmp     byte ptr [rbx+1AAh], 0
0x14000e74d  mov     esi, 10h
0x14000e752  jz      short loc_14000E762
0x14000e754  cmp     qword ptr [rbx+1B0h], 0
0x14000e75c  jz      short loc_14000E76C
0x14000e75e  xor     edi, edi
0x14000e760  jmp     short loc_14000E7C2
0x14000e762  cmp     qword ptr [rbx+158h], 0
0x14000e76a  jnz     short loc_14000E776
0x14000e76c  mov     edi, 0C000000Eh
0x14000e771  jmp     loc_14000E84C
0x14000e776  mov     rcx, [rbx+168h]; Pdo
0x14000e77d  lea     rax, [rsp+78h+var_38]
0x14000e782  mov     [rsp+78h+Type], rax; Type
0x14000e787  lea     rdx, DEVPKEY_Device_ClassGuid; PropertyKey
0x14000e78e  lea     rax, [rsp+78h+var_34]
0x14000e793  xor     r9d, r9d; Flags
0x14000e796  mov     [rsp+78h+RequiredSize], rax; RequiredSize
0x14000e79b  xor     r8d, r8d; Lcid
0x14000e79e  lea     rax, [rsp+78h+Buf1]
0x14000e7a3  mov     [rsp+78h+Data], rax; Data
0x14000e7a8  mov     dword ptr [rsp+78h+Timeout], esi; Size
0x14000e7ac  call    cs:__imp_IoGetDevicePropertyData
0x14000e7b3  nop     dword ptr [rax+rax+00h]
0x14000e7b8  mov     edi, eax
0x14000e7ba  test    eax, eax
0x14000e7bc  js      loc_14000E84C
0x14000e7c2  mov     r8, rsi; Size
0x14000e7c5  lea     rdx, GUID_DEVCLASS_SMRDISK; Buf2
0x14000e7cc  lea     rcx, [rsp+78h+Buf1]; Buf1
0x14000e7d1  call    memcmp
0x14000e7d6  test    eax, eax
0x14000e7d8  jnz     short loc_14000E7E3
0x14000e7da  lea     rsi, aSmrVolume; "SMR\\Volume"
0x14000e7e1  jmp     short loc_14000E7F5
0x14000e7e3  bt      qword ptr [rbx+138h], 3Ah ; ':'
0x14000e7ec  jnb     short loc_14000E7FC
0x14000e7ee  lea     rsi, aScmVolume; "SCM\\Volume"
0x14000e7f5  mov     ebx, 16h
0x14000e7fa  jmp     short loc_14000E808
0x14000e7fc  lea     rsi, aStorageVolume; "STORAGE\\Volume"
0x14000e803  mov     ebx, 1Eh
0x14000e808  lea     rdx, [rbx+2]
0x14000e80c  mov     ecx, 102h
0x14000e811  mov     r8d, 20204D56h
0x14000e817  call    cs:__imp_ExAllocatePool2
0x14000e81e  nop     dword ptr [rax+rax+00h]
0x14000e823  mov     [r14], rax
0x14000e826  test    rax, rax
0x14000e829  jnz     short loc_14000E832
0x14000e82b  mov     edi, 0C000009Ah
0x14000e830  jmp     short loc_14000E84C
0x14000e832  mov     r8, rbx; Size
0x14000e835  mov     rdx, rsi; Src
0x14000e838  mov     rcx, rax; void *
0x14000e83b  call    memmove
0x14000e840  mov     rdx, [r14]
0x14000e843  shr     rbx, 1
0x14000e846  xor     eax, eax
0x14000e848  mov     [rdx+rbx*2], ax
0x14000e84c  xor     edx, edx; Wait
0x14000e84e  mov     rcx, rbp; Mutex
0x14000e851  call    cs:__imp_KeReleaseMutex
0x14000e858  nop     dword ptr [rax+rax+00h]
0x14000e85d  mov     eax, edi
0x14000e85f  mov     rcx, [rsp+78h+var_20]
0x14000e864  xor     rcx, rsp; StackCookie
0x14000e867  call    __security_check_cookie
0x14000e86c  lea     r11, [rsp+78h+var_18]
0x14000e871  mov     rbx, [r11+30h]
0x14000e875  mov     rbp, [r11+38h]
0x14000e879  mov     rsp, r11
0x14000e87c  pop     r14
0x14000e87e  pop     rdi
0x14000e87f  pop     rsi
0x14000e880  retn
```
