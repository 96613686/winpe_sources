# VmpQueryInstanceId(VM_VOLUME_EXTENSION *,ushort * *)

- ea: `0x140016010`
- end: `0x140016129`
- name: `?VmpQueryInstanceId@@YAJPEAVVM_VOLUME_EXTENSION@@PEAPEAG@Z`
- size: `281`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140015f70`

## callees

- `0x140005050`
- `0x140005090`
- `0x140016010`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400160fb`
- `ntoskrnl!KeReleaseMutex` at `0x1400160fb`
- `ntoskrnl!RtlStringFromGUID` at `0x1400160a9`
- `ntoskrnl!RtlStringFromGUID` at `0x1400160a9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001605d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001605d`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400160dc`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400160dc`

## pseudocode

```c
__int64 __fastcall VmpQueryInstanceId(struct VM_VOLUME_EXTENSION *a1, unsigned __int16 **a2)
{
  struct _KMUTANT *v2; // rdi
  NTSTATUS v5; // eax
  __int64 v6; // rdx
  unsigned int v7; // ebx
  struct _UNICODE_STRING GuidString; // [rsp+30h] [rbp-38h] BYREF
  GUID Guid; // [rsp+40h] [rbp-28h] BYREF

  v2 = (struct _KMUTANT *)((char *)a1 + 56);
  *a2 = 0;
  Guid = 0;
  GuidString = 0;
  KeWaitForSingleObject((char *)a1 + 56, Executive, 0, 0, 0);
  if ( *((_BYTE *)a1 + 426) )
  {
    if ( *((_QWORD *)a1 + 54) )
    {
      (*(void (__fastcall **)(_QWORD, GUID *))(*((_QWORD *)VmRootExtension + 49) + 120LL))(*((_QWORD *)a1 + 54), &Guid);
      v5 = RtlStringFromGUID(&Guid, &GuidString);
      goto LABEL_7;
    }
LABEL_5:
    v7 = -1073741810;
    goto LABEL_9;
  }
  v6 = *((_QWORD *)a1 + 43);
  if ( !v6 )
    goto LABEL_5;
  v5 = RtlDuplicateUnicodeString(1u, (PCUNICODE_STRING)(*(_QWORD *)(v6 + 64) + 48LL), &GuidString);
LABEL_7:
  v7 = v5;
  if ( v5 >= 0 )
    *a2 = GuidString.Buffer;
LABEL_9:
  KeReleaseMutex(v2, 0);
  return v7;
}

```

## disassembly

```asm
0x140016010  mov     [rsp+arg_10], rbx
0x140016015  mov     [rsp+arg_18], rsi
0x14001601a  push    rdi
0x14001601b  sub     rsp, 60h
0x14001601f  mov     rax, cs:__security_cookie
0x140016026  xor     rax, rsp
0x140016029  mov     [rsp+68h+var_18], rax
0x14001602e  xor     eax, eax
0x140016030  lea     rdi, [rcx+38h]
0x140016034  mov     [rdx], rax
0x140016037  mov     rsi, rdx
0x14001603a  mov     rbx, rcx
0x14001603d  mov     [rsp+68h+Timeout], rax; Timeout
0x140016042  xorps   xmm0, xmm0
0x140016045  xorps   xmm1, xmm1
0x140016048  xor     edx, edx; WaitReason
0x14001604a  xor     r9d, r9d; Alertable
0x14001604d  xor     r8d, r8d; WaitMode
0x140016050  mov     rcx, rdi; Object
0x140016053  movups  xmmword ptr [rsp+68h+Guid.Data1], xmm0
0x140016058  movups  xmmword ptr [rsp+68h+GuidString.Length], xmm1
0x14001605d  call    cs:__imp_KeWaitForSingleObject
0x140016064  nop     dword ptr [rax+rax+00h]
0x140016069  cmp     byte ptr [rbx+1AAh], 0
0x140016070  jz      short loc_1400160B7
0x140016072  cmp     qword ptr [rbx+1B0h], 0
0x14001607a  jz      short loc_1400160C3
0x14001607c  mov     rax, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x140016083  lea     rdx, [rsp+68h+Guid]
0x140016088  mov     rcx, [rax+188h]
0x14001608f  mov     rax, [rcx+78h]
0x140016093  mov     rcx, [rbx+1B0h]
0x14001609a  call    _guard_dispatch_icall
0x14001609f  lea     rdx, [rsp+68h+GuidString]; GuidString
0x1400160a4  lea     rcx, [rsp+68h+Guid]; Guid
0x1400160a9  call    cs:__imp_RtlStringFromGUID
0x1400160b0  nop     dword ptr [rax+rax+00h]
0x1400160b5  jmp     short loc_1400160E8
0x1400160b7  mov     rdx, [rbx+158h]
0x1400160be  test    rdx, rdx
0x1400160c1  jnz     short loc_1400160CA
0x1400160c3  mov     ebx, 0C000000Eh
0x1400160c8  jmp     short loc_1400160F6
0x1400160ca  mov     rdx, [rdx+40h]
0x1400160ce  lea     r8, [rsp+68h+GuidString]; StringOut
0x1400160d3  add     rdx, 30h ; '0'; StringIn
0x1400160d7  mov     ecx, 1; Flags
0x1400160dc  call    cs:__imp_RtlDuplicateUnicodeString
0x1400160e3  nop     dword ptr [rax+rax+00h]
0x1400160e8  mov     ebx, eax
0x1400160ea  test    eax, eax
0x1400160ec  js      short loc_1400160F6
0x1400160ee  mov     rax, [rsp+68h+GuidString.Buffer]
0x1400160f3  mov     [rsi], rax
0x1400160f6  xor     edx, edx; Wait
0x1400160f8  mov     rcx, rdi; Mutex
0x1400160fb  call    cs:__imp_KeReleaseMutex
0x140016102  nop     dword ptr [rax+rax+00h]
0x140016107  mov     eax, ebx
0x140016109  mov     rcx, [rsp+68h+var_18]
0x14001610e  xor     rcx, rsp; StackCookie
0x140016111  call    __security_check_cookie
0x140016116  lea     r11, [rsp+68h+var_8]
0x14001611b  mov     rbx, [r11+20h]
0x14001611f  mov     rsi, [r11+28h]
0x140016123  mov     rsp, r11
0x140016126  pop     rdi
0x140016127  retn
```
