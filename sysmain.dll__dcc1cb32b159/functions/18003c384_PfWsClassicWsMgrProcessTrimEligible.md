# PfWsClassicWsMgrProcessTrimEligible

- ea: `0x18003c384`
- end: `0x18003c464`
- name: `PfWsClassicWsMgrProcessTrimEligible`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18003c250`

## callees

- `0x18003c384`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c459`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c459`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003c3e8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003c3e8`
- `api-ms-win-containers-cmclient-l1-5-1!CmsIsContainerMemoryHostingProcessTrimEligible` at `0x18003c428`
- `api-ms-win-containers-cmclient-l1-5-1!CmsIsContainerMemoryHostingProcessTrimEligible` at `0x18003c428`
- `api-ms-win-containers-cmclient-l1-5-1!CmsOpenContainerByMemoryHostingProcess` at `0x18003c407`
- `api-ms-win-containers-cmclient-l1-5-1!CmsOpenContainerByMemoryHostingProcess` at `0x18003c407`
- `api-ms-win-containers-cmclient-l1-1-0!CmsCloseContainer` at `0x18003c447`
- `api-ms-win-containers-cmclient-l1-1-0!CmsCloseContainer` at `0x18003c447`

## pseudocode

```c
__int64 __fastcall PfWsClassicWsMgrProcessTrimEligible(__int64 a1, __int64 a2)
{
  DWORD v3; // r8d
  int v4; // eax
  HANDLE v6; // rax
  void *v7; // rbx
  int v8; // eax
  unsigned int v9; // [rsp+38h] [rbp+10h] BYREF
  __int64 v10; // [rsp+40h] [rbp+18h] BYREF

  v3 = *(_DWORD *)(a2 + 4);
  v9 = 0;
  v10 = 0;
  if ( v3 == *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 4144LL) )
    return v9;
  v4 = *(_DWORD *)(a2 + 92);
  if ( (v4 & 0x10) != 0 )
  {
    if ( (*(_BYTE *)(a1 + 4) & 4) == 0 )
      return 1;
    v6 = OpenProcess(0x1000u, 0, v3);
    v7 = v6;
    if ( v6 )
    {
      v8 = CmsOpenContainerByMemoryHostingProcess(v6, 30, 1, &v10);
      if ( v8 >= 0 )
      {
        if ( (int)CmsIsContainerMemoryHostingProcessTrimEligible(v10, &v9) >= 0 )
        {
LABEL_13:
          if ( v10 )
            CmsCloseContainer(&v10);
          if ( v7 )
            CloseHandle(v7);
          return v9;
        }
      }
      else if ( v8 == -2147467263 )
      {
        *(_DWORD *)(a1 + 4) &= ~4u;
      }
    }
    v9 = 1;
    goto LABEL_13;
  }
  if ( (v4 & 0xA) != 0xA )
    return 1;
  return v9;
}

```

## disassembly

```asm
0x18003c384  mov     [rsp+arg_0], rbx
0x18003c389  push    rdi
0x18003c38a  sub     rsp, 20h
0x18003c38e  mov     rax, cs:PfSvcGlobals
0x18003c395  mov     rdi, rcx
0x18003c398  mov     r8d, [rdx+4]; dwProcessId
0x18003c39c  mov     [rsp+28h+arg_8], 0
0x18003c3a4  mov     [rsp+28h+arg_10], 0
0x18003c3ad  cmp     r8d, [rax+1030h]
0x18003c3b4  jz      short loc_18003C3CC
0x18003c3b6  mov     eax, [rdx+5Ch]
0x18003c3b9  test    al, 10h
0x18003c3bb  jnz     short loc_18003C3DB
0x18003c3bd  and     eax, 0Ah
0x18003c3c0  cmp     al, 0Ah
0x18003c3c2  jz      short loc_18003C3CC
0x18003c3c4  mov     [rsp+28h+arg_8], 1
0x18003c3cc  mov     eax, [rsp+28h+arg_8]
0x18003c3d0  mov     rbx, [rsp+28h+arg_0]
0x18003c3d5  add     rsp, 20h
0x18003c3d9  pop     rdi
0x18003c3da  retn
0x18003c3db  test    byte ptr [rcx+4], 4
0x18003c3df  jz      short loc_18003C3C4
0x18003c3e1  xor     edx, edx; bInheritHandle
0x18003c3e3  mov     ecx, 1000h; dwDesiredAccess
0x18003c3e8  call    cs:__imp_OpenProcess
0x18003c3ee  mov     rbx, rax
0x18003c3f1  test    rax, rax
0x18003c3f4  jz      short loc_18003C432
0x18003c3f6  mov     edx, 1Eh
0x18003c3fb  lea     r9, [rsp+28h+arg_10]
0x18003c400  mov     rcx, rax
0x18003c403  lea     r8d, [rdx-1Dh]
0x18003c407  call    cs:__imp_CmsOpenContainerByMemoryHostingProcess
0x18003c40d  test    eax, eax
0x18003c40f  jns     short loc_18003C41E
0x18003c411  cmp     eax, 80004001h
0x18003c416  jnz     short loc_18003C432
0x18003c418  and     dword ptr [rdi+4], 0FFFFFFFBh
0x18003c41c  jmp     short loc_18003C432
0x18003c41e  mov     rcx, [rsp+28h+arg_10]
0x18003c423  lea     rdx, [rsp+28h+arg_8]
0x18003c428  call    cs:__imp_CmsIsContainerMemoryHostingProcessTrimEligible
0x18003c42e  test    eax, eax
0x18003c430  jns     short loc_18003C43A
0x18003c432  mov     [rsp+28h+arg_8], 1
0x18003c43a  cmp     [rsp+28h+arg_10], 0
0x18003c440  jz      short loc_18003C44D
0x18003c442  lea     rcx, [rsp+28h+arg_10]
0x18003c447  call    cs:__imp_CmsCloseContainer
0x18003c44d  test    rbx, rbx
0x18003c450  jz      loc_18003C3CC
0x18003c456  mov     rcx, rbx; hObject
0x18003c459  call    cs:__imp_CloseHandle
0x18003c45f  jmp     loc_18003C3CC
```
