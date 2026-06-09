# VmQueryWmiDataBlock

- ea: `0x1400163e0`
- end: `0x140016536`
- name: `VmQueryWmiDataBlock`
- size: `342`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, PIRP Irp@<rdx>, int, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002aa0`
- `0x140005050`
- `0x140005090`
- `0x140005240`
- `0x1400163e0`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x140016507`
- `WMILIB!WmiCompleteRequest` at `0x140016507`

## pseudocode

```c
NTSTATUS __fastcall VmQueryWmiDataBlock(
        PDEVICE_OBJECT DeviceObject,
        PIRP Irp,
        int a3,
        __int64 a4,
        int a5,
        ULONG *a6,
        unsigned int a7,
        __int64 a8)
{
  ULONG v8; // ebx
  NTSTATUS v11; // ebp
  _QWORD *DeviceExtension; // rdi
  __int64 v13; // rax
  size_t v14; // rsi
  wchar_t pszDest[40]; // [rsp+30h] [rbp-98h] BYREF

  v8 = 0;
  if ( a3 )
  {
    v11 = -1073741163;
  }
  else
  {
    DeviceExtension = DeviceObject->DeviceExtension;
    if ( *((_BYTE *)DeviceExtension + 161) )
    {
      RtlStringCbPrintfW(pszDest, 0x50u, L"\\Device\\HarddiskVolume%d", *((unsigned int *)DeviceExtension + 41));
      v13 = -1;
      do
        ++v13;
      while ( pszDest[v13] );
      v14 = (unsigned __int16)(2 * v13);
      v8 = v14 + 90;
      if ( a7 >= (int)v14 + 90 )
      {
        v11 = 0;
        (*(void (__fastcall **)(_QWORD, __int64, const wchar_t *, _QWORD))(DeviceExtension[1] + 336LL))(
          DeviceExtension[28],
          a8,
          L"VOLMGR  ",
          *((unsigned int *)DeviceExtension + 41));
        *(_WORD *)(a8 + 88) = v14;
        memmove((void *)(a8 + 90), pszDest, v14);
        *a6 = v8;
      }
      else
      {
        v11 = -1073741789;
      }
    }
    else
    {
      v11 = -1073741823;
    }
  }
  return WmiCompleteRequest(DeviceObject, Irp, v11, v8, 0);
}

```

## disassembly

```asm
0x1400163e0  push    rbx
0x1400163e2  push    rbp
0x1400163e3  push    r12
0x1400163e5  push    r13
0x1400163e7  push    r14
0x1400163e9  push    r15
0x1400163eb  sub     rsp, 98h
0x1400163f2  mov     rax, cs:__security_cookie
0x1400163f9  xor     rax, rsp
0x1400163fc  mov     [rsp+0C8h+var_48], rax
0x140016404  mov     r12, [rsp+0C8h+arg_28]
0x14001640c  xor     ebx, ebx
0x14001640e  mov     r13, [rsp+0C8h+arg_38]
0x140016416  mov     r15, rdx
0x140016419  mov     r14, rcx
0x14001641c  test    r8d, r8d
0x14001641f  jz      short loc_14001642B
0x140016421  mov     ebp, 0C0000295h
0x140016426  jmp     loc_1400164F6
0x14001642b  mov     [rsp+0C8h+var_38], rdi
0x140016433  mov     rdi, [rcx+40h]
0x140016437  movzx   eax, byte ptr [rdi+0A1h]
0x14001643e  test    al, al
0x140016440  jnz     short loc_14001644C
0x140016442  mov     ebp, 0C0000001h
0x140016447  jmp     loc_1400164EE
0x14001644c  mov     r9d, [rdi+0A4h]
0x140016453  lea     r8, aDeviceHarddisk; "\\Device\\HarddiskVolume%d"
0x14001645a  mov     edx, 50h ; 'P'; cbDest
0x14001645f  mov     [rsp+0C8h+arg_10], rsi
0x140016467  lea     rcx, [rsp+0C8h+pszDest]; pszDest
0x14001646c  call    RtlStringCbPrintfW
0x140016471  lea     rcx, [rsp+0C8h+pszDest]
0x140016476  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14001647d  nop     dword ptr [rax]
0x140016480  inc     rax
0x140016483  cmp     [rcx+rax*2], bx
0x140016487  jnz     short loc_140016480
0x140016489  add     ax, ax
0x14001648c  movzx   esi, ax
0x14001648f  lea     ebx, [rsi+5Ah]
0x140016492  cmp     [rsp+0C8h+arg_30], ebx
0x140016499  jnb     short loc_1400164A2
0x14001649b  mov     ebp, 0C0000023h
0x1400164a0  jmp     short loc_1400164E6
0x1400164a2  mov     rax, [rdi+8]
0x1400164a6  lea     r8, aVolmgr; "VOLMGR  "
0x1400164ad  mov     r9d, [rdi+0A4h]
0x1400164b4  mov     rdx, r13
0x1400164b7  mov     rcx, [rdi+0E0h]
0x1400164be  xor     ebp, ebp
0x1400164c0  mov     rax, [rax+150h]
0x1400164c7  call    _guard_dispatch_icall
0x1400164cc  mov     r8, rsi; Size
0x1400164cf  mov     [r13+58h], si
0x1400164d4  lea     rcx, [r13+5Ah]; void *
0x1400164d8  lea     rdx, [rsp+0C8h+pszDest]; Src
0x1400164dd  call    memmove
0x1400164e2  mov     [r12], ebx
0x1400164e6  mov     rsi, [rsp+0C8h+arg_10]
0x1400164ee  mov     rdi, [rsp+0C8h+var_38]
0x1400164f6  mov     r9d, ebx; BufferUsed
0x1400164f9  mov     [rsp+0C8h+PriorityBoost], 0; PriorityBoost
0x1400164fe  mov     r8d, ebp; Status
0x140016501  mov     rdx, r15; Irp
0x140016504  mov     rcx, r14; DeviceObject
0x140016507  call    cs:__imp_WmiCompleteRequest
0x14001650e  nop     dword ptr [rax+rax+00h]
0x140016513  mov     rcx, [rsp+0C8h+var_48]
0x14001651b  xor     rcx, rsp; StackCookie
0x14001651e  call    __security_check_cookie
0x140016523  add     rsp, 98h
0x14001652a  pop     r15
0x14001652c  pop     r14
0x14001652e  pop     r13
0x140016530  pop     r12
0x140016532  pop     rbp
0x140016533  pop     rbx
0x140016534  retn
```
