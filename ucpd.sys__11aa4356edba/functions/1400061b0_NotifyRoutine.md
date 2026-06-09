# NotifyRoutine

- ea: `0x1400061b0`
- end: `0x1400062ce`
- name: `NotifyRoutine`
- size: `286`
- prototype: `void __stdcall(PEPROCESS Process, HANDLE ProcessId, PPS_CREATE_NOTIFY_INFO CreateInfo)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x1400061b0`
- `0x140006430`
- `0x140006828`
- `0x1400129f0`
- `0x14001424c`
- `0x14001442c`
- `0x1400146b0`
- `0x140016a40`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140006263`
- `ntoskrnl!ExAcquireFastMutex` at `0x140006263`
- `ntoskrnl!ExReleaseFastMutex` at `0x140006291`
- `ntoskrnl!ExReleaseFastMutex` at `0x140006291`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14000627b`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14000627b`

## pseudocode

```c
void __fastcall NotifyRoutine(PEPROCESS Process, HANDLE ProcessId, PPS_CREATE_NOTIFY_INFO CreateInfo)
{
  PCUNICODE_STRING ImageFileName; // rcx
  __int64 *v6; // rbx
  _QWORD Buffer[2]; // [rsp+30h] [rbp-48h] BYREF
  __int128 v8; // [rsp+40h] [rbp-38h]
  __int128 v9; // [rsp+50h] [rbp-28h]
  __int64 v10; // [rsp+60h] [rbp-18h]

  if ( !byte_140021840 )
  {
    if ( CreateInfo )
    {
      ImageFileName = CreateInfo->ImageFileName;
      if ( ImageFileName )
      {
        if ( (unsigned int)sub_1400129F0(
                             ImageFileName->Buffer,
                             (unsigned __int64)ImageFileName->Length >> 1,
                             (unsigned int)L"winlogon.exe",
                             12,
                             1) != -1 )
        {
          sub_1400146B0();
          byte_140021840 = 1;
        }
      }
    }
  }
  if ( (unsigned int)sub_14001442C(&dword_140021798) )
  {
    if ( CreateInfo )
    {
      sub_140006828(ProcessId, CreateInfo);
    }
    else
    {
      Buffer[0] = 0;
      Buffer[1] = ProcessId;
      v8 = 0;
      v10 = 0;
      v9 = 0;
      ExAcquireFastMutex(&FastMutex);
      v6 = (__int64 *)RtlLookupElementGenericTableAvl(&Table, Buffer);
      ExReleaseFastMutex(&FastMutex);
      if ( v6 )
        sub_140006430(v6);
      sub_14001424C(ProcessId);
    }
  }
}

```

## disassembly

```asm
0x1400061b0  mov     [rsp+arg_0], rbx
0x1400061b5  push    rdi
0x1400061b6  sub     rsp, 70h
0x1400061ba  mov     rax, cs:__security_cookie
0x1400061c1  xor     rax, rsp
0x1400061c4  mov     [rsp+78h+var_10], rax
0x1400061c9  cmp     cs:byte_140021840, 0
0x1400061d0  mov     rbx, r8
0x1400061d3  mov     rdi, rdx
0x1400061d6  jnz     short loc_140006218
0x1400061d8  test    rbx, rbx
0x1400061db  jz      short loc_140006218
0x1400061dd  mov     rcx, [r8+30h]
0x1400061e1  test    rcx, rcx
0x1400061e4  jz      short loc_140006218
0x1400061e6  movzx   edx, word ptr [rcx]
0x1400061e9  lea     r8, aWinlogonExe; "winlogon.exe"
0x1400061f0  mov     rcx, [rcx+8]
0x1400061f4  mov     r9d, 0Ch
0x1400061fa  shr     rdx, 1
0x1400061fd  mov     [rsp+78h+var_58], 1
0x140006202  call    sub_1400129F0
0x140006207  cmp     eax, 0FFFFFFFFh
0x14000620a  jz      short loc_140006218
0x14000620c  call    sub_1400146B0
0x140006211  mov     cs:byte_140021840, 1
0x140006218  lea     rcx, dword_140021798
0x14000621f  call    sub_14001442C
0x140006224  test    eax, eax
0x140006226  jz      loc_1400062B2
0x14000622c  test    rbx, rbx
0x14000622f  jz      short loc_14000623E
0x140006231  mov     rdx, rbx
0x140006234  mov     rcx, rdi
0x140006237  call    sub_140006828
0x14000623c  jmp     short loc_1400062B2
0x14000623e  xorps   xmm0, xmm0
0x140006241  lea     rcx, FastMutex; FastMutex
0x140006248  xor     eax, eax
0x14000624a  movups  [rsp+78h+Buffer], xmm0
0x14000624f  mov     qword ptr [rsp+78h+Buffer+8], rdi
0x140006254  movups  [rsp+78h+var_38], xmm0
0x140006259  mov     [rsp+78h+var_18], rax
0x14000625e  movups  [rsp+78h+var_28], xmm0
0x140006263  call    cs:ExAcquireFastMutex
0x14000626a  nop     dword ptr [rax+rax+00h]
0x14000626f  lea     rdx, [rsp+78h+Buffer]; Buffer
0x140006274  lea     rcx, Table; Table
0x14000627b  call    cs:RtlLookupElementGenericTableAvl
0x140006282  nop     dword ptr [rax+rax+00h]
0x140006287  lea     rcx, FastMutex; FastMutex
0x14000628e  mov     rbx, rax
0x140006291  call    cs:ExReleaseFastMutex
0x140006298  nop     dword ptr [rax+rax+00h]
0x14000629d  test    rbx, rbx
0x1400062a0  jz      short loc_1400062AA
0x1400062a2  mov     rcx, rbx; P
0x1400062a5  call    sub_140006430
0x1400062aa  mov     rcx, rdi
0x1400062ad  call    sub_14001424C
0x1400062b2  mov     rcx, [rsp+78h+var_10]
0x1400062b7  xor     rcx, rsp; StackCookie
0x1400062ba  call    __security_check_cookie
0x1400062bf  mov     rbx, [rsp+78h+arg_0]
0x1400062c7  add     rsp, 70h
0x1400062cb  pop     rdi
0x1400062cc  retn
```
