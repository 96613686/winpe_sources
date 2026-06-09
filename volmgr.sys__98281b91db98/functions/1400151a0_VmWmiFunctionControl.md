# VmWmiFunctionControl

- ea: `0x1400151a0`
- end: `0x140015232`
- name: `VmWmiFunctionControl`
- size: `146`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, PIRP Irp@<rdx>, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005090`
- `0x1400151a0`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x14001521c`
- `WMILIB!WmiCompleteRequest` at `0x14001521c`

## pseudocode

```c
NTSTATUS __fastcall VmWmiFunctionControl(PDEVICE_OBJECT DeviceObject, PIRP Irp, int a3, int a4, char a5)
{
  NTSTATUS v7; // edi
  _QWORD *DeviceExtension; // rbx
  char *v9; // rcx
  __int64 v10; // rax

  if ( a3 )
  {
    v7 = -1073741163;
  }
  else
  {
    v7 = 0;
    if ( a4 == 1 )
    {
      DeviceExtension = DeviceObject->DeviceExtension;
      v9 = (char *)(DeviceExtension + 28);
      v10 = DeviceExtension[1];
      if ( a5 )
      {
        v7 = (*(__int64 (__fastcall **)(char *))(v10 + 304))(v9);
        if ( v7 >= 0 )
          *((_BYTE *)DeviceExtension + 161) = 1;
      }
      else
      {
        *((_BYTE *)DeviceExtension + 161) = (*(__int64 (__fastcall **)(char *, _QWORD))(v10 + 312))(v9, 0);
      }
    }
  }
  return WmiCompleteRequest(DeviceObject, Irp, v7, 0, 0);
}

```

## disassembly

```asm
0x1400151a0  push    rbx
0x1400151a2  push    rbp
0x1400151a3  push    rsi
0x1400151a4  push    rdi
0x1400151a5  sub     rsp, 38h
0x1400151a9  mov     rbp, rdx
0x1400151ac  mov     rsi, rcx
0x1400151af  test    r8d, r8d
0x1400151b2  jnz     short loc_140015206
0x1400151b4  xor     edi, edi
0x1400151b6  cmp     r9d, 1
0x1400151ba  jnz     short loc_14001520B
0x1400151bc  mov     rbx, [rcx+40h]
0x1400151c0  lea     rcx, [rbx+0E0h]
0x1400151c7  mov     rax, [rbx+8]
0x1400151cb  cmp     [rsp+58h+arg_20], dil
0x1400151d3  jnz     short loc_1400151EB
0x1400151d5  mov     rax, [rax+138h]
0x1400151dc  xor     edx, edx
0x1400151de  call    _guard_dispatch_icall
0x1400151e3  mov     [rbx+0A1h], al
0x1400151e9  jmp     short loc_14001520B
0x1400151eb  mov     rax, [rax+130h]
0x1400151f2  call    _guard_dispatch_icall
0x1400151f7  mov     edi, eax
0x1400151f9  test    eax, eax
0x1400151fb  js      short loc_14001520B
0x1400151fd  mov     byte ptr [rbx+0A1h], 1
0x140015204  jmp     short loc_14001520B
0x140015206  mov     edi, 0C0000295h
0x14001520b  xor     r9d, r9d; BufferUsed
0x14001520e  mov     [rsp+58h+PriorityBoost], 0; PriorityBoost
0x140015213  mov     r8d, edi; Status
0x140015216  mov     rdx, rbp; Irp
0x140015219  mov     rcx, rsi; DeviceObject
0x14001521c  call    cs:__imp_WmiCompleteRequest
0x140015223  nop     dword ptr [rax+rax+00h]
0x140015228  add     rsp, 38h
0x14001522c  pop     rdi
0x14001522d  pop     rsi
0x14001522e  pop     rbp
0x14001522f  pop     rbx
0x140015230  retn
```
