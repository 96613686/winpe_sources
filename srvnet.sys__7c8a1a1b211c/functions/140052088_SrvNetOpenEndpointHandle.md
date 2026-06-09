# SrvNetOpenEndpointHandle

- ea: `0x140052088`
- end: `0x140052188`
- name: `SrvNetOpenEndpointHandle`
- size: `256`
- prototype: `__int64 __fastcall(PVOID DeviceName, PVOID Name, PHANDLE FileHandle, PVOID *Object)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140051970`

## callees

- `0x14001389c`
- `0x14002a3e0`
- `0x140052088`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x140052141`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140052141`
- `ntoskrnl!ZwClose` at `0x140052156`
- `ntoskrnl!ZwClose` at `0x140052156`
- `TDI!TdiOpenNetbiosAddress` at `0x1400520cc`
- `TDI!TdiOpenNetbiosAddress` at `0x1400520cc`

## pseudocode

```c
__int64 __fastcall SrvNetOpenEndpointHandle(PVOID DeviceName, PVOID Name, PHANDLE FileHandle, PVOID *Object)
{
  NTSTATUS v6; // esi
  UCHAR Buffer[16]; // [rsp+30h] [rbp-58h] BYREF
  __int128 v9; // [rsp+40h] [rbp-48h]
  _BYTE v10[23]; // [rsp+50h] [rbp-38h] BYREF

  memset(v10, 0, sizeof(v10));
  *(_OWORD *)Buffer = 0;
  v9 = 0;
  v6 = TdiOpenNetbiosAddress(FileHandle, Buffer, DeviceName, Name);
  if ( v6 >= 0 )
  {
    v6 = ObReferenceObjectByHandle(*FileHandle, 0, 0, 0, Object, 0);
    if ( v6 < 0 )
    {
      ZwClose(*FileHandle);
      *Object = 0;
      *FileHandle = 0;
    }
  }
  else
  {
    *FileHandle = 0;
    *Object = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        WPP_8d73355e5e233ce540e4603b97b45138_Traceguids,
        (unsigned int)v6);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140052088  push    rbx
0x14005208a  push    rsi
0x14005208b  push    rdi
0x14005208c  sub     rsp, 70h
0x140052090  mov     rax, cs:__security_cookie
0x140052097  xor     rax, rsp
0x14005209a  mov     [rsp+88h+var_20], rax
0x14005209f  xorps   xmm0, xmm0
0x1400520a2  mov     rbx, r8
0x1400520a5  mov     rdi, r9
0x1400520a8  mov     r8, rcx; DeviceName
0x1400520ab  mov     r9, rdx; Name
0x1400520ae  xor     eax, eax
0x1400520b0  movups  xmmword ptr [rsp+88h+var_38], xmm0
0x1400520b5  lea     rdx, [rsp+88h+Buffer]; Buffer
0x1400520ba  mov     qword ptr [rsp+88h+var_38+0Fh], rax
0x1400520bf  mov     rcx, rbx; FileHandle
0x1400520c2  movups  xmmword ptr [rsp+88h+Buffer], xmm0
0x1400520c7  movups  [rsp+88h+var_48], xmm0
0x1400520cc  call    cs:__imp_TdiOpenNetbiosAddress
0x1400520d3  nop     dword ptr [rax+rax+00h]
0x1400520d8  mov     esi, eax
0x1400520da  test    eax, eax
0x1400520dc  jns     short loc_140052128
0x1400520de  mov     qword ptr [rbx], 0
0x1400520e5  mov     qword ptr [rdi], 0
0x1400520ec  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400520f3  lea     rax, WPP_GLOBAL_Control
0x1400520fa  cmp     rcx, rax
0x1400520fd  jz      short loc_140052170
0x1400520ff  test    dword ptr [rcx+2Ch], 100h
0x140052106  jz      short loc_140052170
0x140052108  cmp     byte ptr [rcx+29h], 1
0x14005210c  jb      short loc_140052170
0x14005210e  mov     rcx, [rcx+18h]
0x140052112  lea     r8, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids
0x140052119  mov     edx, 0Ch
0x14005211e  mov     r9d, esi
0x140052121  call    WPP_SF_d
0x140052126  jmp     short loc_140052170
0x140052128  mov     rcx, [rbx]; Handle
0x14005212b  xor     r9d, r9d; AccessMode
0x14005212e  mov     [rsp+88h+HandleInformation], 0; HandleInformation
0x140052137  xor     r8d, r8d; ObjectType
0x14005213a  xor     edx, edx; DesiredAccess
0x14005213c  mov     [rsp+88h+Object], rdi; Object
0x140052141  call    cs:__imp_ObReferenceObjectByHandle
0x140052148  nop     dword ptr [rax+rax+00h]
0x14005214d  mov     esi, eax
0x14005214f  test    eax, eax
0x140052151  jns     short loc_140052170
0x140052153  mov     rcx, [rbx]; Handle
0x140052156  call    cs:__imp_ZwClose
0x14005215d  nop     dword ptr [rax+rax+00h]
0x140052162  mov     qword ptr [rdi], 0
0x140052169  mov     qword ptr [rbx], 0
0x140052170  mov     eax, esi
0x140052172  mov     rcx, [rsp+88h+var_20]
0x140052177  xor     rcx, rsp; StackCookie
0x14005217a  call    __security_check_cookie
0x14005217f  add     rsp, 70h
0x140052183  pop     rdi
0x140052184  pop     rsi
0x140052185  pop     rbx
0x140052186  retn
```
