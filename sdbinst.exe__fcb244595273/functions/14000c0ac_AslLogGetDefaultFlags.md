# AslLogGetDefaultFlags

- ea: `0x14000c0ac`
- end: `0x14000c18b`
- name: `AslLogGetDefaultFlags`
- size: `223`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000b574`

## callees

- `0x14000c0ac`
- `0x140010568`
- `0x140010a68`

## import_xrefs

- `ntdll!ZwClose` at `0x14000c11c`
- `ntdll!ZwClose` at `0x14000c173`
- `ntdll!ZwClose` at `0x14000c11c`
- `ntdll!ZwClose` at `0x14000c173`

## string_xrefs

- `0x14000c0e2`: `\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x14000c130`: `\OSDATA\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`

## pseudocode

```c
__int64 AslLogGetDefaultFlags()
{
  unsigned int v0; // edi
  HANDLE v1; // rbx
  int Key; // eax
  int UInt32; // eax
  int v4; // eax
  unsigned int v6; // [rsp+40h] [rbp+10h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp+18h] BYREF

  v0 = 0;
  v1 = 0;
  v6 = 0;
  Handle = 0;
  if ( byte_140042B38 )
  {
    v0 = dword_140042B28;
  }
  else
  {
    Key = AslRegistryGetKey(&Handle, L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags", 1);
    v1 = Handle;
    if ( Key < 0 || (UInt32 = AslRegistryGetUInt32(&v6, Handle, L"LogFlags"), v0 = v6, UInt32 < 0) )
    {
      if ( v1 )
      {
        ZwClose(v1);
        Handle = 0;
      }
      v4 = AslRegistryGetKey(&Handle, L"\\OSDATA\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags", 1);
      v1 = Handle;
      if ( v4 >= 0 )
      {
        AslRegistryGetUInt32(&v6, Handle, L"LogFlags");
        v0 = v6;
      }
    }
  }
  dword_140042B28 = v0;
  byte_140042B38 = 1;
  if ( v1 )
    ZwClose(v1);
  return v0;
}

```

## disassembly

```asm
0x14000c0ac  mov     [rsp-8+arg_10], rbx
0x14000c0b1  mov     [rsp-8+arg_18], rdi
0x14000c0b6  push    rbp
0x14000c0b7  mov     rbp, rsp
0x14000c0ba  sub     rsp, 30h
0x14000c0be  xor     edi, edi
0x14000c0c0  xor     ebx, ebx
0x14000c0c2  cmp     cs:byte_140042B38, bl
0x14000c0c8  mov     [rbp+arg_0], edi
0x14000c0cb  mov     [rbp+Handle], rbx
0x14000c0cf  jz      short loc_14000C0DC
0x14000c0d1  mov     edi, cs:dword_140042B28
0x14000c0d7  jmp     loc_14000C15E
0x14000c0dc  mov     r8d, 1
0x14000c0e2  lea     rdx, aSoftwareMicros_1; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x14000c0e9  lea     rcx, [rbp+Handle]
0x14000c0ed  call    AslRegistryGetKey
0x14000c0f2  mov     rbx, [rbp+Handle]
0x14000c0f6  test    eax, eax
0x14000c0f8  js      short loc_14000C114
0x14000c0fa  lea     r8, aLogflags; "LogFlags"
0x14000c101  mov     rdx, rbx
0x14000c104  lea     rcx, [rbp+arg_0]
0x14000c108  call    AslRegistryGetUInt32
0x14000c10d  mov     edi, [rbp+arg_0]
0x14000c110  test    eax, eax
0x14000c112  jns     short loc_14000C15E
0x14000c114  test    rbx, rbx
0x14000c117  jz      short loc_14000C12A
0x14000c119  mov     rcx, rbx; Handle
0x14000c11c  call    cs:__imp_ZwClose
0x14000c122  mov     [rbp+Handle], 0
0x14000c12a  mov     r8d, 1
0x14000c130  lea     rdx, aOsdataSoftware; "\\OSDATA\\Software\\Microsoft\\Windows "...
0x14000c137  lea     rcx, [rbp+Handle]
0x14000c13b  call    AslRegistryGetKey
0x14000c140  mov     rbx, [rbp+Handle]
0x14000c144  test    eax, eax
0x14000c146  js      short loc_14000C15E
0x14000c148  lea     r8, aLogflags; "LogFlags"
0x14000c14f  mov     rdx, rbx
0x14000c152  lea     rcx, [rbp+arg_0]
0x14000c156  call    AslRegistryGetUInt32
0x14000c15b  mov     edi, [rbp+arg_0]
0x14000c15e  mov     cs:dword_140042B28, edi
0x14000c164  mov     cs:byte_140042B38, 1
0x14000c16b  test    rbx, rbx
0x14000c16e  jz      short loc_14000C179
0x14000c170  mov     rcx, rbx; Handle
0x14000c173  call    cs:__imp_ZwClose
0x14000c179  mov     rbx, [rsp+30h+arg_10]
0x14000c17e  mov     eax, edi
0x14000c180  mov     rdi, [rsp+30h+arg_18]
0x14000c185  add     rsp, 30h
0x14000c189  pop     rbp
0x14000c18a  retn
```
