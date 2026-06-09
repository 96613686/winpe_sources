# SetAsRunning(bool)

- ea: `0x14000f55c`
- end: `0x14000f5b2`
- name: `?SetAsRunning@@YAX_N@Z`
- size: `86`
- prototype: `void __fastcall(bool)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140012f54`

## callees

- `0x14000f55c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000f595`
- `KERNEL32!CloseHandle` at `0x14000f595`
- `KERNEL32!CreateEventW` at `0x14000f574`
- `KERNEL32!CreateEventW` at `0x14000f574`

## string_xrefs

- `0x14000f567`: `Local\EaseOfAccessDialog`

## pseudocode

```c
void __fastcall SetAsRunning(char a1)
{
  if ( a1 )
  {
    hObject = CreateEventW(0, 1, 0, L"Local\\EaseOfAccessDialog");
  }
  else if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
}

```

## disassembly

```asm
0x14000f55c  sub     rsp, 28h
0x14000f560  test    cl, cl
0x14000f562  jz      short loc_14000F589
0x14000f564  xor     r8d, r8d; bInitialState
0x14000f567  lea     r9, aLocalEaseofacc; "Local\\EaseOfAccessDialog"
0x14000f56e  xor     ecx, ecx; lpEventAttributes
0x14000f570  lea     edx, [r8+1]; bManualReset
0x14000f574  call    cs:__imp_CreateEventW
0x14000f57b  nop     dword ptr [rax+rax+00h]
0x14000f580  mov     cs:hObject, rax
0x14000f587  jmp     short loc_14000F5AC
0x14000f589  mov     rcx, cs:hObject; hObject
0x14000f590  test    rcx, rcx
0x14000f593  jz      short loc_14000F5AC
0x14000f595  call    cs:__imp_CloseHandle
0x14000f59c  nop     dword ptr [rax+rax+00h]
0x14000f5a1  mov     cs:hObject, 0
0x14000f5ac  add     rsp, 28h
0x14000f5b0  retn
```
