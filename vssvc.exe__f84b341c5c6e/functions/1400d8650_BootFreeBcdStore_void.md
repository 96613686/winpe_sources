# BootFreeBcdStore(void)

- ea: `0x1400d8650`
- end: `0x1400d876e`
- name: `?BootFreeBcdStore@@YAHXZ`
- size: `286`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14006168c`

## callees

- `0x140021ca0`
- `0x1400235a8`
- `0x1400d257c`
- `0x1400d7ebc`
- `0x1400d8650`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d875b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d875b`
- `bcd!BcdCloseStore` at `0x1400d873e`
- `bcd!BcdCloseStore` at `0x1400d873e`
- `bcd!BcdOpenSystemStore` at `0x1400d8674`
- `bcd!BcdOpenSystemStore` at `0x1400d86af`
- `bcd!BcdOpenSystemStore` at `0x1400d8674`
- `bcd!BcdOpenSystemStore` at `0x1400d86af`
- `bcd!BcdForciblyUnloadStore` at `0x1400d86e5`
- `bcd!BcdForciblyUnloadStore` at `0x1400d8718`
- `bcd!BcdForciblyUnloadStore` at `0x1400d86e5`
- `bcd!BcdForciblyUnloadStore` at `0x1400d8718`

## string_xrefs

- `0x1400d86b8`: `::BcdOpenSystemStore(&hStoreHandle)`

## pseudocode

```c
__int64 BootFreeBcdStore(void)
{
  int v0; // eax
  unsigned int v1; // ebx
  DWORD v2; // edi
  int v3; // eax
  int v4; // eax
  int v5; // eax
  __int64 v7; // [rsp+40h] [rbp+8h] BYREF

  TraceFunctionEnter(L"BootFreeBcdStore");
  v7 = 0;
  v0 = BcdOpenSystemStore(&v7);
  if ( v0 >= 0 )
  {
    v4 = BcdForciblyUnloadStore(v7);
    if ( v4 >= 0 )
    {
      v2 = 0;
      v7 = 0;
      v1 = 1;
    }
    else
    {
      v1 = 0;
      v2 = WIN32_FROM_NTSTATUS((unsigned int)v4);
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v5 = BcdForciblyUnloadStore(v7);
        WPP_SF_Ds(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          39,
          (unsigned int)WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids,
          v5,
          "::BcdForciblyUnloadStore(hStoreHandle)");
      }
    }
  }
  else
  {
    v1 = 0;
    v2 = WIN32_FROM_NTSTATUS((unsigned int)v0);
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v3 = BcdOpenSystemStore(&v7);
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        38,
        (unsigned int)WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids,
        v3,
        "::BcdOpenSystemStore(&hStoreHandle)");
    }
  }
  if ( v7 )
  {
    BcdCloseStore();
    v7 = 0;
  }
  TraceFunctionExit(L"BootFreeBcdStore");
  SetLastError(v2);
  return v1;
}

```

## disassembly

```asm
0x1400d8650  mov     [rsp+arg_8], rbx
0x1400d8655  push    rdi
0x1400d8656  sub     rsp, 30h
0x1400d865a  lea     rcx, aBootfreebcdsto; "BootFreeBcdStore"
0x1400d8661  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x1400d8666  lea     rcx, [rsp+38h+arg_0]
0x1400d866b  mov     [rsp+38h+arg_0], 0
0x1400d8674  call    cs:__imp_BcdOpenSystemStore
0x1400d867a  test    eax, eax
0x1400d867c  jns     short loc_1400D86E0
0x1400d867e  xor     ebx, ebx
0x1400d8680  mov     ecx, eax
0x1400d8682  call    WIN32_FROM_NTSTATUS
0x1400d8687  mov     edi, eax
0x1400d8689  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d8690  lea     rax, WPP_GLOBAL_Control
0x1400d8697  cmp     rcx, rax
0x1400d869a  jz      loc_1400D8734
0x1400d86a0  test    byte ptr [rcx+1Ch], 8
0x1400d86a4  jz      loc_1400D8734
0x1400d86aa  lea     rcx, [rsp+38h+arg_0]
0x1400d86af  call    cs:__imp_BcdOpenSystemStore
0x1400d86b5  lea     edx, [rbx+26h]
0x1400d86b8  lea     rcx, aBcdopensystems_0; "::BcdOpenSystemStore(&hStoreHandle)"
0x1400d86bf  mov     [rsp+38h+var_18], rcx
0x1400d86c4  lea     r8, WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids
0x1400d86cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d86d2  mov     r9d, eax
0x1400d86d5  mov     rcx, [rcx+10h]
0x1400d86d9  call    WPP_SF_Ds
0x1400d86de  jmp     short loc_1400D8734
0x1400d86e0  mov     rcx, [rsp+38h+arg_0]
0x1400d86e5  call    cs:__imp_BcdForciblyUnloadStore
0x1400d86eb  test    eax, eax
0x1400d86ed  jns     short loc_1400D872A
0x1400d86ef  xor     ebx, ebx
0x1400d86f1  mov     ecx, eax
0x1400d86f3  call    WIN32_FROM_NTSTATUS
0x1400d86f8  mov     edi, eax
0x1400d86fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d8701  lea     rax, WPP_GLOBAL_Control
0x1400d8708  cmp     rcx, rax
0x1400d870b  jz      short loc_1400D8734
0x1400d870d  test    byte ptr [rcx+1Ch], 8
0x1400d8711  jz      short loc_1400D8734
0x1400d8713  mov     rcx, [rsp+38h+arg_0]
0x1400d8718  call    cs:__imp_BcdForciblyUnloadStore
0x1400d871e  lea     edx, [rbx+27h]
0x1400d8721  lea     rcx, aBcdforciblyunl_0; "::BcdForciblyUnloadStore(hStoreHandle)"
0x1400d8728  jmp     short loc_1400D86BF
0x1400d872a  xor     edi, edi
0x1400d872c  mov     [rsp+38h+arg_0], rdi
0x1400d8731  lea     ebx, [rdi+1]
0x1400d8734  mov     rcx, [rsp+38h+arg_0]
0x1400d8739  test    rcx, rcx
0x1400d873c  jz      short loc_1400D874D
0x1400d873e  call    cs:__imp_BcdCloseStore
0x1400d8744  mov     [rsp+38h+arg_0], 0
0x1400d874d  lea     rcx, aBootfreebcdsto; "BootFreeBcdStore"
0x1400d8754  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x1400d8759  mov     ecx, edi; dwErrCode
0x1400d875b  call    cs:__imp_SetLastError
0x1400d8761  mov     eax, ebx
0x1400d8763  mov     rbx, [rsp+38h+arg_8]
0x1400d8768  add     rsp, 30h
0x1400d876c  pop     rdi
0x1400d876d  retn
```
