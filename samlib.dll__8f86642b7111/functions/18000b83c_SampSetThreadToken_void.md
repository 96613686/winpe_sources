# SampSetThreadToken(void *)

- ea: `0x18000b83c`
- end: `0x18000b8c5`
- name: `?SampSetThreadToken@@YAJPEAX@Z`
- size: `137`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180013490`

## callees

- `0x1800078c0`
- `0x18000807c`
- `0x18000b83c`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18000b85c`
- `ntdll!NtSetInformationThread` at `0x18000b85c`

## pseudocode

```c
__int64 __fastcall SampSetThreadToken(void *a1)
{
  NTSTATUS v1; // eax
  unsigned int v2; // ebx
  void *ThreadInformation; // [rsp+30h] [rbp+8h] BYREF

  ThreadInformation = a1;
  v1 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  v2 = v1;
  if ( v1 >= 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 373, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
  }
  else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      372,
      &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
      (unsigned int)v1);
  }
  return v2;
}

```

## disassembly

```asm
0x18000b83c  mov     [rsp+ThreadInformation], rcx
0x18000b841  push    rbx
0x18000b842  sub     rsp, 20h
0x18000b846  mov     r9d, 8; ThreadInformationLength
0x18000b84c  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x18000b851  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000b858  lea     edx, [r9-3]; ThreadInformationClass
0x18000b85c  call    cs:__imp_NtSetInformationThread
0x18000b862  mov     ebx, eax
0x18000b864  test    eax, eax
0x18000b866  jns     short loc_18000B895
0x18000b868  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b86f  test    byte ptr [rcx+1Ch], 2
0x18000b873  jz      short loc_18000B8BD
0x18000b875  cmp     byte ptr [rcx+19h], 2
0x18000b879  jb      short loc_18000B8BD
0x18000b87b  mov     rcx, [rcx+10h]
0x18000b87f  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000b886  mov     edx, 174h
0x18000b88b  mov     r9d, eax
0x18000b88e  call    WPP_SF_D
0x18000b893  jmp     short loc_18000B8BD
0x18000b895  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b89c  test    byte ptr [rcx+1Ch], 2
0x18000b8a0  jz      short loc_18000B8BD
0x18000b8a2  cmp     byte ptr [rcx+19h], 4
0x18000b8a6  jb      short loc_18000B8BD
0x18000b8a8  mov     rcx, [rcx+10h]
0x18000b8ac  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000b8b3  mov     edx, 175h
0x18000b8b8  call    WPP_SF_
0x18000b8bd  mov     eax, ebx
0x18000b8bf  add     rsp, 20h
0x18000b8c3  pop     rbx
0x18000b8c4  retn
```
