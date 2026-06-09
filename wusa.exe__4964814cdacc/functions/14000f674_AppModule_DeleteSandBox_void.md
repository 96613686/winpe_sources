# AppModule::DeleteSandBox(void)

- ea: `0x14000f674`
- end: `0x14000f6eb`
- name: `?DeleteSandBox@AppModule@@QEAAXXZ`
- size: `119`
- prototype: `void __fastcall(AppModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400075b0`
- `0x1400108dc`

## callees

- `0x140001258`
- `0x14000f674`
- `0x140012b00`
- `0x140013490`

## string_xrefs

- `0x14000f695`: `AppModule::DeleteSandBox`
- `0x14000f6bd`: `AppModule::DeleteSandBox`
- `0x14000f6b1`: `Failed to delete sandbox`

## pseudocode

```c
void __fastcall AppModule::DeleteSandBox(AppModule *this)
{
  const wchar_t *v1; // r9
  void *v3; // rcx

  v1 = (const wchar_t *)*((_QWORD *)this + 22);
  if ( v1 )
  {
    WusaLogDebugEventA(L"AppModule::DeleteSandBox", 295, "Deleting sandbox %S", v1);
    if ( (int)WusaSandBoxClean(*((const unsigned __int16 **)this + 22)) < 0 )
      WusaLogDebugEventA(L"AppModule::DeleteSandBox", 300, "Failed to delete sandbox");
    v3 = (void *)*((_QWORD *)this + 22);
    if ( v3 )
    {
      operator delete(v3);
      *((_QWORD *)this + 22) = 0;
    }
  }
}

```

## disassembly

```asm
0x14000f674  push    rbx
0x14000f676  sub     rsp, 20h
0x14000f67a  mov     r9, [rcx+0B0h]
0x14000f681  mov     rbx, rcx
0x14000f684  test    r9, r9
0x14000f687  jz      short loc_14000F6E5
0x14000f689  lea     r8, aDeletingSandbo; "Deleting sandbox %S"
0x14000f690  mov     edx, 127h
0x14000f695  lea     rcx, aAppmoduleDelet; "AppModule::DeleteSandBox"
0x14000f69c  call    WusaLogDebugEventA
0x14000f6a1  mov     rcx, [rbx+0B0h]; unsigned __int16 *
0x14000f6a8  call    ?WusaSandBoxClean@@YAJPEBG@Z; WusaSandBoxClean(ushort const *)
0x14000f6ad  test    eax, eax
0x14000f6af  jns     short loc_14000F6C9
0x14000f6b1  lea     r8, aFailedToDelete_0; "Failed to delete sandbox"
0x14000f6b8  mov     edx, 12Ch
0x14000f6bd  lea     rcx, aAppmoduleDelet; "AppModule::DeleteSandBox"
0x14000f6c4  call    WusaLogDebugEventA
0x14000f6c9  mov     rcx, [rbx+0B0h]; Block
0x14000f6d0  test    rcx, rcx
0x14000f6d3  jz      short loc_14000F6E5
0x14000f6d5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000f6da  mov     qword ptr [rbx+0B0h], 0
0x14000f6e5  add     rsp, 20h
0x14000f6e9  pop     rbx
0x14000f6ea  retn
```
