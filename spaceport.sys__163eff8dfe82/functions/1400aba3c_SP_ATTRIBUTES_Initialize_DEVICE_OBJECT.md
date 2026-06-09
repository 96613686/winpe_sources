# SP_ATTRIBUTES::Initialize(_DEVICE_OBJECT *)

- ea: `0x1400aba3c`
- end: `0x1400abb6a`
- name: `?Initialize@SP_ATTRIBUTES@@QEAAJPEAU_DEVICE_OBJECT@@@Z`
- size: `302`
- prototype: `__int64 __fastcall(SP_ATTRIBUTES *__hidden this, struct _DEVICE_OBJECT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400a2ad0`

## callees

- `0x140068600`
- `0x14008c760`
- `0x1400aba3c`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400ababc`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400abb2f`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400ababc`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400abb2f`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1400abaff`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1400abaff`
- `ntoskrnl!ZwClose` at `0x1400abb4a`
- `ntoskrnl!ZwClose` at `0x1400abb4a`

## pseudocode

```c
__int64 __fastcall SP_ATTRIBUTES::Initialize(SP_ATTRIBUTES *this, struct _DEVICE_OBJECT *a2)
{
  int RegistryValues; // ebx
  _QWORD v5[15]; // [rsp+30h] [rbp-78h] BYREF

  memset(v5, 0, 112);
  RegistryValues = SP_WORKITEM::Initialize(
                     (SP_ATTRIBUTES *)((char *)this + 208),
                     a2,
                     (int (*)(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *))SP_ATTRIBUTES::Callback,
                     this);
  if ( RegistryValues >= 0 )
  {
    v5[0] = SP_ATTRIBUTES::QueryRoutine;
    RegistryValues = RtlQueryRegistryValuesEx(1, L"Spaceport\\Parameters", v5, this, 0);
    if ( (int)(RegistryValues + 0x80000000) < 0 || RegistryValues == -1073741772 )
    {
      RegistryValues = IoOpenDriverRegistryKey(*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 1), 1, 1);
      if ( RegistryValues >= 0 )
        return (unsigned int)RtlQueryRegistryValuesEx(0x40000000, 0, v5, this, 0);
    }
  }
  return (unsigned int)RegistryValues;
}

```

## disassembly

```asm
0x1400aba3c  mov     rax, rsp
0x1400aba3f  mov     [rax+10h], rbx
0x1400aba43  push    rdi
0x1400aba44  sub     rsp, 0A0h
0x1400aba4b  mov     rbx, rdx
0x1400aba4e  mov     qword ptr [rax+8], 0
0x1400aba56  xor     edx, edx; Val
0x1400aba58  mov     qword ptr [rax-78h], 0
0x1400aba60  mov     rdi, rcx
0x1400aba63  lea     rcx, [rax-70h]; void *
0x1400aba67  lea     r8d, [rdx+68h]; Size
0x1400aba6b  call    memset
0x1400aba70  lea     rcx, [rdi+0D0h]; this
0x1400aba77  mov     r9, rdi; void *
0x1400aba7a  lea     r8, ?Callback@SP_ATTRIBUTES@@CAJPEAU_DEVICE_OBJECT@@PEAU_LIST_ENTRY@@1PEAX@Z; int (*)(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *)
0x1400aba81  mov     rdx, rbx; struct _DEVICE_OBJECT *
0x1400aba84  call    ?Initialize@SP_WORKITEM@@QEAAJPEAU_DEVICE_OBJECT@@P6AJ0PEAU_LIST_ENTRY@@1PEAX@Z2@Z; SP_WORKITEM::Initialize(_DEVICE_OBJECT *,long (*)(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *),void *)
0x1400aba89  mov     ebx, eax
0x1400aba8b  test    eax, eax
0x1400aba8d  js      loc_1400ABB3D
0x1400aba93  lea     rax, ?QueryRoutine@SP_ATTRIBUTES@@CAJPEAGKPEAXK11@Z; SP_ATTRIBUTES::QueryRoutine(ushort *,ulong,void *,ulong,void *,void *)
0x1400aba9a  mov     [rsp+0A8h+var_88], 0
0x1400abaa3  mov     r9, rdi
0x1400abaa6  mov     [rsp+0A8h+var_78], rax
0x1400abaab  lea     r8, [rsp+0A8h+var_78]
0x1400abab0  mov     ecx, 1
0x1400abab5  lea     rdx, Path; "Spaceport\\Parameters"
0x1400ababc  call    cs:__imp_RtlQueryRegistryValuesEx
0x1400abac3  nop     dword ptr [rax+rax+00h]
0x1400abac8  mov     ecx, 80000000h
0x1400abacd  mov     ebx, eax
0x1400abacf  add     eax, ecx
0x1400abad1  test    ecx, eax
0x1400abad3  jnz     short loc_1400ABADD
0x1400abad5  cmp     ebx, 0C0000034h
0x1400abadb  jnz     short loc_1400ABB3D
0x1400abadd  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400abae4  lea     rax, [rsp+0A8h+Handle]
0x1400abaec  xor     r9d, r9d
0x1400abaef  mov     [rsp+0A8h+var_88], rax
0x1400abaf4  mov     rcx, [rcx+8]
0x1400abaf8  lea     edx, [r9+1]
0x1400abafc  mov     r8d, edx
0x1400abaff  call    cs:__imp_IoOpenDriverRegistryKey
0x1400abb06  nop     dword ptr [rax+rax+00h]
0x1400abb0b  mov     ebx, eax
0x1400abb0d  test    eax, eax
0x1400abb0f  js      short loc_1400ABB3D
0x1400abb11  mov     rdx, [rsp+0A8h+Handle]
0x1400abb19  lea     r8, [rsp+0A8h+var_78]
0x1400abb1e  mov     r9, rdi
0x1400abb21  mov     [rsp+0A8h+var_88], 0
0x1400abb2a  mov     ecx, 40000000h
0x1400abb2f  call    cs:__imp_RtlQueryRegistryValuesEx
0x1400abb36  nop     dword ptr [rax+rax+00h]
0x1400abb3b  mov     ebx, eax
0x1400abb3d  mov     rcx, [rsp+0A8h+Handle]; Handle
0x1400abb45  test    rcx, rcx
0x1400abb48  jz      short loc_1400ABB56
0x1400abb4a  call    cs:__imp_ZwClose
0x1400abb51  nop     dword ptr [rax+rax+00h]
0x1400abb56  mov     eax, ebx
0x1400abb58  mov     rbx, [rsp+0A8h+arg_8]
0x1400abb60  add     rsp, 0A0h
0x1400abb67  pop     rdi
0x1400abb68  retn
```
