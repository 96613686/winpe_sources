# SP_ATTRIBUTES::Initialize(_DEVICE_OBJECT *)

- ea: `0x1400ab89c`
- end: `0x1400ab9ca`
- name: `?Initialize@SP_ATTRIBUTES@@QEAAJPEAU_DEVICE_OBJECT@@@Z`
- size: `302`
- prototype: `__int64 __fastcall(SP_ATTRIBUTES *__hidden this, struct _DEVICE_OBJECT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400a29a0`

## callees

- `0x1400684c0`
- `0x14008c760`
- `0x1400ab89c`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400ab91c`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400ab98f`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400ab91c`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400ab98f`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1400ab95f`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1400ab95f`
- `ntoskrnl!ZwClose` at `0x1400ab9aa`
- `ntoskrnl!ZwClose` at `0x1400ab9aa`

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
0x1400ab89c  mov     rax, rsp
0x1400ab89f  mov     [rax+10h], rbx
0x1400ab8a3  push    rdi
0x1400ab8a4  sub     rsp, 0A0h
0x1400ab8ab  mov     rbx, rdx
0x1400ab8ae  mov     qword ptr [rax+8], 0
0x1400ab8b6  xor     edx, edx; Val
0x1400ab8b8  mov     qword ptr [rax-78h], 0
0x1400ab8c0  mov     rdi, rcx
0x1400ab8c3  lea     rcx, [rax-70h]; void *
0x1400ab8c7  lea     r8d, [rdx+68h]; Size
0x1400ab8cb  call    memset
0x1400ab8d0  lea     rcx, [rdi+0D0h]; this
0x1400ab8d7  mov     r9, rdi; void *
0x1400ab8da  lea     r8, ?Callback@SP_ATTRIBUTES@@CAJPEAU_DEVICE_OBJECT@@PEAU_LIST_ENTRY@@1PEAX@Z; int (*)(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *)
0x1400ab8e1  mov     rdx, rbx; struct _DEVICE_OBJECT *
0x1400ab8e4  call    ?Initialize@SP_WORKITEM@@QEAAJPEAU_DEVICE_OBJECT@@P6AJ0PEAU_LIST_ENTRY@@1PEAX@Z2@Z; SP_WORKITEM::Initialize(_DEVICE_OBJECT *,long (*)(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *),void *)
0x1400ab8e9  mov     ebx, eax
0x1400ab8eb  test    eax, eax
0x1400ab8ed  js      loc_1400AB99D
0x1400ab8f3  lea     rax, ?QueryRoutine@SP_ATTRIBUTES@@CAJPEAGKPEAXK11@Z; SP_ATTRIBUTES::QueryRoutine(ushort *,ulong,void *,ulong,void *,void *)
0x1400ab8fa  mov     [rsp+0A8h+var_88], 0
0x1400ab903  mov     r9, rdi
0x1400ab906  mov     [rsp+0A8h+var_78], rax
0x1400ab90b  lea     r8, [rsp+0A8h+var_78]
0x1400ab910  mov     ecx, 1
0x1400ab915  lea     rdx, Path; "Spaceport\\Parameters"
0x1400ab91c  call    cs:__imp_RtlQueryRegistryValuesEx
0x1400ab923  nop     dword ptr [rax+rax+00h]
0x1400ab928  mov     ecx, 80000000h
0x1400ab92d  mov     ebx, eax
0x1400ab92f  add     eax, ecx
0x1400ab931  test    ecx, eax
0x1400ab933  jnz     short loc_1400AB93D
0x1400ab935  cmp     ebx, 0C0000034h
0x1400ab93b  jnz     short loc_1400AB99D
0x1400ab93d  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400ab944  lea     rax, [rsp+0A8h+Handle]
0x1400ab94c  xor     r9d, r9d
0x1400ab94f  mov     [rsp+0A8h+var_88], rax
0x1400ab954  mov     rcx, [rcx+8]
0x1400ab958  lea     edx, [r9+1]
0x1400ab95c  mov     r8d, edx
0x1400ab95f  call    cs:__imp_IoOpenDriverRegistryKey
0x1400ab966  nop     dword ptr [rax+rax+00h]
0x1400ab96b  mov     ebx, eax
0x1400ab96d  test    eax, eax
0x1400ab96f  js      short loc_1400AB99D
0x1400ab971  mov     rdx, [rsp+0A8h+Handle]
0x1400ab979  lea     r8, [rsp+0A8h+var_78]
0x1400ab97e  mov     r9, rdi
0x1400ab981  mov     [rsp+0A8h+var_88], 0
0x1400ab98a  mov     ecx, 40000000h
0x1400ab98f  call    cs:__imp_RtlQueryRegistryValuesEx
0x1400ab996  nop     dword ptr [rax+rax+00h]
0x1400ab99b  mov     ebx, eax
0x1400ab99d  mov     rcx, [rsp+0A8h+Handle]; Handle
0x1400ab9a5  test    rcx, rcx
0x1400ab9a8  jz      short loc_1400AB9B6
0x1400ab9aa  call    cs:__imp_ZwClose
0x1400ab9b1  nop     dword ptr [rax+rax+00h]
0x1400ab9b6  mov     eax, ebx
0x1400ab9b8  mov     rbx, [rsp+0A8h+arg_8]
0x1400ab9c0  add     rsp, 0A0h
0x1400ab9c7  pop     rdi
0x1400ab9c8  retn
```
