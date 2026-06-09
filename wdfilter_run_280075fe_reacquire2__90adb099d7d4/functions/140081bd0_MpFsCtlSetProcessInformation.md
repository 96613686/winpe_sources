# MpFsCtlSetProcessInformation

- ea: `0x140081bd0`
- end: `0x140081d9f`
- name: `MpFsCtlSetProcessInformation`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400448f0`

## callees

- `0x14000da0c`
- `0x140030060`
- `0x14003a1b0`
- `0x140064160`
- `0x140081bd0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140081bfc`
- `ntoskrnl!ProbeForRead` at `0x140081c21`
- `ntoskrnl!ProbeForRead` at `0x140081bfc`
- `ntoskrnl!ProbeForRead` at `0x140081c21`
- `ntoskrnl!IoGetCurrentProcess` at `0x140081c54`
- `ntoskrnl!IoGetCurrentProcess` at `0x140081c54`

## pseudocode

```c
__int64 __fastcall MpFsCtlSetProcessInformation(__int64 a1)
{
  unsigned int *v2; // rbx
  __int64 result; // rax
  struct _KPROCESS *CurrentProcess; // rax
  unsigned int v5; // edi
  volatile signed __int32 *v6; // [rsp+58h] [rbp+10h] BYREF

  v6 = 0;
  ProbeForRead(*(volatile void **)(*(_QWORD *)(a1 + 16) + 48LL), 0x18u, 4u);
  v2 = *(unsigned int **)(*(_QWORD *)(a1 + 16) + 48LL);
  ProbeForRead(v2, v2[1], 4u);
  if ( v2[2] - 1 > 2 )
    return 3221225485LL;
  if ( v2[4] < 4 )
    return 3221225476LL;
  if ( v2[3] == -1 )
  {
    CurrentProcess = IoGetCurrentProcess();
    result = MpGetProcessContextByObject(CurrentProcess, &v6);
  }
  else
  {
    result = MpGetProcessContextById((void *)v2[3], &v6);
  }
  if ( (int)result >= 0 )
  {
    v5 = v2[5];
    switch ( v2[2] )
    {
      case 1u:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_dDD(
            WPP_GLOBAL_Control->AttachedDevice,
            34,
            *((unsigned int *)v6 + 13),
            v2[3],
            *((_DWORD *)v6 + 13),
            v2[5],
            v2);
        *((_DWORD *)v6 + 13) = v5;
        break;
      case 2u:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_dDD(
            WPP_GLOBAL_Control->AttachedDevice,
            35,
            *((unsigned int *)v6 + 14),
            v2[3],
            *((_DWORD *)v6 + 14),
            v2[5],
            v2);
        *((_DWORD *)v6 + 14) = v5;
        break;
      case 3u:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_dDD(
            WPP_GLOBAL_Control->AttachedDevice,
            36,
            *((unsigned int *)v6 + 15),
            v2[3],
            *((_DWORD *)v6 + 15),
            v2[5],
            v2);
        *((_DWORD *)v6 + 15) = v5;
        break;
    }
    MpReleaseProcessContext(v6);
    return 0;
  }
  else
  {
    _mm_lfence();
  }
  return result;
}

```

## disassembly

```asm
0x140081bd0  mov     [rsp+arg_0], rbx
0x140081bd5  mov     [rsp+arg_8], rdx
0x140081bda  push    rdi
0x140081bdb  sub     rsp, 40h
0x140081bdf  mov     rbx, rcx
0x140081be2  mov     [rsp+48h+arg_8], 0
0x140081beb  mov     rcx, [rcx+10h]
0x140081bef  mov     edx, 18h; Length
0x140081bf4  lea     r8d, [rdx-14h]; Alignment
0x140081bf8  mov     rcx, [rcx+30h]; Address
0x140081bfc  call    cs:__imp_ProbeForRead
0x140081c03  nop     dword ptr [rax+rax+00h]
0x140081c08  mov     rax, [rbx+10h]
0x140081c0c  mov     rbx, [rax+30h]
0x140081c10  mov     [rsp+48h+var_18], rbx
0x140081c15  mov     edx, [rbx+4]; Length
0x140081c18  mov     r8d, 4; Alignment
0x140081c1e  mov     rcx, rbx; Address
0x140081c21  call    cs:__imp_ProbeForRead
0x140081c28  nop     dword ptr [rax+rax+00h]
0x140081c2d  nop
0x140081c2e  mov     eax, [rbx+8]
0x140081c31  dec     eax
0x140081c33  cmp     eax, 2
0x140081c36  ja      loc_140081D8C
0x140081c3c  cmp     dword ptr [rbx+10h], 4
0x140081c40  jnb     short loc_140081C4C
0x140081c42  mov     eax, 0C0000004h
0x140081c47  jmp     loc_140081D93
0x140081c4c  mov     eax, [rbx+0Ch]
0x140081c4f  cmp     eax, 0FFFFFFFFh
0x140081c52  jnz     short loc_140081C6F
0x140081c54  call    cs:__imp_IoGetCurrentProcess
0x140081c5b  nop     dword ptr [rax+rax+00h]
0x140081c60  mov     rcx, rax; Process
0x140081c63  lea     rdx, [rsp+48h+arg_8]
0x140081c68  call    MpGetProcessContextByObject
0x140081c6d  jmp     short loc_140081C7C
0x140081c6f  mov     rcx, rax
0x140081c72  lea     rdx, [rsp+48h+arg_8]
0x140081c77  call    MpGetProcessContextById
0x140081c7c  test    eax, eax
0x140081c7e  jns     short loc_140081C88
0x140081c80  lfence
0x140081c83  jmp     loc_140081D93
0x140081c88  mov     edi, [rbx+14h]
0x140081c8b  mov     ecx, [rbx+8]
0x140081c8e  sub     ecx, 1
0x140081c91  jz      loc_140081D38
0x140081c97  sub     ecx, 1
0x140081c9a  jz      short loc_140081CF0
0x140081c9c  cmp     ecx, 1
0x140081c9f  jnz     loc_140081D7E
0x140081ca5  lea     rax, WPP_GLOBAL_Control
0x140081cac  mov     rcx, cs:WPP_GLOBAL_Control
0x140081cb3  cmp     rcx, rax
0x140081cb6  jz      short loc_140081CE3
0x140081cb8  mov     eax, [rcx+2Ch]
0x140081cbb  test    al, 4
0x140081cbd  jz      short loc_140081CE3
0x140081cbf  mov     edx, 24h ; '$'
0x140081cc4  mov     [rsp+48h+var_20], edi
0x140081cc8  mov     rax, [rsp+48h+arg_8]
0x140081ccd  mov     r8d, [rax+3Ch]
0x140081cd1  mov     [rsp+48h+var_28], r8d
0x140081cd6  mov     r9d, [rbx+0Ch]
0x140081cda  mov     rcx, [rcx+18h]
0x140081cde  call    WPP_SF_dDD
0x140081ce3  mov     rax, [rsp+48h+arg_8]
0x140081ce8  mov     [rax+3Ch], edi
0x140081ceb  jmp     loc_140081D7E
0x140081cf0  lea     rax, WPP_GLOBAL_Control
0x140081cf7  mov     rcx, cs:WPP_GLOBAL_Control
0x140081cfe  cmp     rcx, rax
0x140081d01  jz      short loc_140081D2E
0x140081d03  mov     eax, [rcx+2Ch]
0x140081d06  test    al, 4
0x140081d08  jz      short loc_140081D2E
0x140081d0a  mov     edx, 23h ; '#'
0x140081d0f  mov     [rsp+48h+var_20], edi
0x140081d13  mov     rax, [rsp+48h+arg_8]
0x140081d18  mov     r8d, [rax+38h]
0x140081d1c  mov     [rsp+48h+var_28], r8d
0x140081d21  mov     r9d, [rbx+0Ch]
0x140081d25  mov     rcx, [rcx+18h]
0x140081d29  call    WPP_SF_dDD
0x140081d2e  mov     rax, [rsp+48h+arg_8]
0x140081d33  mov     [rax+38h], edi
0x140081d36  jmp     short loc_140081D7E
0x140081d38  lea     rax, WPP_GLOBAL_Control
0x140081d3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140081d46  cmp     rcx, rax
0x140081d49  jz      short loc_140081D76
0x140081d4b  mov     eax, [rcx+2Ch]
0x140081d4e  test    al, 4
0x140081d50  jz      short loc_140081D76
0x140081d52  mov     edx, 22h ; '"'
0x140081d57  mov     [rsp+48h+var_20], edi
0x140081d5b  mov     rax, [rsp+48h+arg_8]
0x140081d60  mov     r8d, [rax+34h]
0x140081d64  mov     [rsp+48h+var_28], r8d
0x140081d69  mov     r9d, [rbx+0Ch]
0x140081d6d  mov     rcx, [rcx+18h]
0x140081d71  call    WPP_SF_dDD
0x140081d76  mov     rax, [rsp+48h+arg_8]
0x140081d7b  mov     [rax+34h], edi
0x140081d7e  mov     rcx, [rsp+48h+arg_8]
0x140081d83  call    MpReleaseProcessContext
0x140081d88  xor     eax, eax
0x140081d8a  jmp     short loc_140081D93
0x140081d8c  mov     eax, 0C000000Dh
0x140081d91  jmp     short $+2
0x140081d93  mov     rbx, [rsp+48h+arg_0]
0x140081d98  add     rsp, 40h
0x140081d9c  pop     rdi
0x140081d9d  retn
```
