# VmpApplySessionId(VM_VOLUME_EXTENSION *)

- ea: `0x14001072c`
- end: `0x14001080e`
- name: `?VmpApplySessionId@@YAJPEAVVM_VOLUME_EXTENSION@@@Z`
- size: `226`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400132f8`

## callees

- `0x14001072c`

## import_xrefs

- `ntoskrnl!IoSetDevicePropertyData` at `0x1400107e5`
- `ntoskrnl!IoSetDevicePropertyData` at `0x1400107e5`
- `ntoskrnl!IoGetDevicePropertyData` at `0x14001079f`
- `ntoskrnl!IoGetDevicePropertyData` at `0x14001079f`

## pseudocode

```c
__int64 __fastcall VmpApplySessionId(PDEVICE_OBJECT *a1)
{
  NTSTATUS v2; // ecx
  NTSTATUS DevicePropertyData; // eax
  int Data; // [rsp+50h] [rbp+8h] BYREF
  ULONG v6; // [rsp+58h] [rbp+10h] BYREF
  DEVPROPTYPE Type; // [rsp+60h] [rbp+18h] BYREF

  Data = 0;
  v2 = 0;
  v6 = 0;
  Type = 0;
  if ( ((*a1)->Flags & 0x600100) == 0 && !*((_BYTE *)a1 + 426) )
  {
    DevicePropertyData = IoGetDevicePropertyData(a1[45], &DEVPKEY_Device_SessionId, 0, 0, 4u, &Data, &v6, &Type);
    if ( DevicePropertyData >= 0 )
    {
      v2 = IoSetDevicePropertyData(*a1, &DEVPKEY_Device_SessionId, 0, 0, Type, v6, &Data);
      if ( v2 >= 0 )
      {
        *((_BYTE *)a1 + 152) = 1;
        *((_BYTE *)a1 + 154) = 1;
      }
    }
    else
    {
      v2 = 0;
      if ( DevicePropertyData != -1073741772 )
        return (unsigned int)DevicePropertyData;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14001072c  mov     r11, rsp
0x14001072f  push    rbx
0x140010730  sub     rsp, 40h
0x140010734  mov     rbx, rcx
0x140010737  mov     [rsp+48h+arg_0], 0
0x14001073f  xor     ecx, ecx
0x140010741  mov     [rsp+48h+arg_8], 0
0x140010749  mov     [rsp+48h+Type], ecx
0x14001074d  mov     rax, [rbx]
0x140010750  mov     edx, [rax+30h]
0x140010753  test    edx, 600100h
0x140010759  jnz     loc_140010805
0x14001075f  cmp     [rbx+1AAh], cl
0x140010765  jnz     loc_140010805
0x14001076b  mov     rcx, [rbx+168h]; Pdo
0x140010772  lea     rax, [r11+18h]
0x140010776  mov     [r11-10h], rax
0x14001077a  lea     rdx, DEVPKEY_Device_SessionId; PropertyKey
0x140010781  lea     rax, [r11+10h]
0x140010785  xor     r9d, r9d; Flags
0x140010788  mov     [r11-18h], rax
0x14001078c  xor     r8d, r8d; Lcid
0x14001078f  lea     rax, [r11+8]
0x140010793  mov     [r11-20h], rax
0x140010797  mov     [rsp+48h+Size], 4; Size
0x14001079f  call    cs:__imp_IoGetDevicePropertyData
0x1400107a6  nop     dword ptr [rax+rax+00h]
0x1400107ab  test    eax, eax
0x1400107ad  jns     short loc_1400107BB
0x1400107af  xor     ecx, ecx
0x1400107b1  cmp     eax, 0C0000034h
0x1400107b6  cmovnz  ecx, eax
0x1400107b9  jmp     short loc_140010805
0x1400107bb  mov     rcx, [rbx]; Pdo
0x1400107be  lea     rax, [rsp+48h+arg_0]
0x1400107c3  mov     [rsp+48h+Data], rax; Data
0x1400107c8  lea     rdx, DEVPKEY_Device_SessionId; PropertyKey
0x1400107cf  mov     eax, [rsp+48h+arg_8]
0x1400107d3  xor     r9d, r9d; Flags
0x1400107d6  mov     [rsp+48h+var_20], eax; Size
0x1400107da  xor     r8d, r8d; Lcid
0x1400107dd  mov     eax, [rsp+48h+Type]
0x1400107e1  mov     [rsp+48h+Size], eax; Type
0x1400107e5  call    cs:__imp_IoSetDevicePropertyData
0x1400107ec  nop     dword ptr [rax+rax+00h]
0x1400107f1  mov     ecx, eax
0x1400107f3  test    eax, eax
0x1400107f5  js      short loc_140010805
0x1400107f7  mov     byte ptr [rbx+98h], 1
0x1400107fe  mov     byte ptr [rbx+9Ah], 1
0x140010805  mov     eax, ecx
0x140010807  add     rsp, 40h
0x14001080b  pop     rbx
0x14001080c  retn
```
