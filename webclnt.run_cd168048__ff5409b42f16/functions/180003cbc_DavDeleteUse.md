# DavDeleteUse

- ea: `0x180003cbc`
- end: `0x180003f84`
- name: `DavDeleteUse`
- size: `712`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x180006670`
- `0x180007b50`

## callees

- `0x180003a9c`
- `0x180003cbc`
- `0x18000591c`
- `0x180006618`
- `0x18000b7dc`
- `0x18000bc5c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180003f3a`
- `ntdll!RtlNtStatusToDosError` at `0x180003f3a`
- `ntdll!NtFsControlFile` at `0x180003df6`
- `ntdll!NtFsControlFile` at `0x180003df6`
- `ntdll!NtClose` at `0x180003e2f`
- `ntdll!NtClose` at `0x180003e2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e63`
- `KERNEL32!LocalFree` at `0x180003f10`
- `KERNEL32!LocalFree` at `0x180003f30`
- `KERNEL32!LocalFree` at `0x180003f10`
- `KERNEL32!LocalFree` at `0x180003f30`

## pseudocode

```c
__int64 __fastcall DavDeleteUse(__int64 a1, unsigned int a2, __int64 a3, unsigned int a4)
{
  __int64 v4; // r14
  ULONG v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  ULONG v9; // esi
  _QWORD *v10; // rcx
  __int64 v11; // r9
  _DWORD *v12; // rax
  __int64 v13; // rcx
  int v14; // eax
  unsigned int v15; // eax
  ULONG v16; // eax
  _QWORD **v17; // rdx
  _QWORD *i; // rcx
  _DWORD *v19; // rcx
  ULONG v20; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-28h] BYREF
  unsigned int InputBuffer; // [rsp+88h] [rbp+10h] BYREF

  InputBuffer = a2;
  v4 = a4;
  IoStatusBlock = 0;
  v6 = DavImpersonateClient();
  v9 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 274, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v6);
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 275, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, InputBuffer);
      v10 = WPP_GLOBAL_Control;
    }
    if ( *(_QWORD *)(a3 + 24) || InputBuffer || (v11 = *(unsigned int *)(a3 + 36), (_DWORD)v11 == 1) )
    {
      v14 = NtFsControlFile(*(HANDLE *)(a3 + 40), 0, 0, 0, &IoStatusBlock, 0x4000020u, &InputBuffer, 4u, 0, 0);
      if ( v14 < 0 )
      {
        v20 = RtlNtStatusToDosError(v14);
        v9 = v20;
        v13 = (__int64)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 277, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v20);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            278,
            WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids,
            *(_QWORD *)(a3 + 40));
        v15 = NtClose(*(HANDLE *)(a3 + 40));
        if ( v15
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 279, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v15);
        }
        CloseHandle(*(HANDLE *)(a3 + 80));
        v16 = DavDeleteSymbolicLink(*(WCHAR **)(a3 + 24), *(LPCWSTR *)(a3 + 48), 0, (HANDLE)0xFFFFFFFFFFFFFFFFLL, 1);
        v9 = v16;
        if ( v16 )
        {
          v13 = (__int64)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 280, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v16);
        }
        else
        {
          v17 = *(_QWORD ***)(DavUseObject + 16 * v4);
          if ( v17 == (_QWORD **)a3 )
          {
            *(_QWORD *)(DavUseObject + 16 * v4) = *(_QWORD *)a3;
          }
          else
          {
            for ( i = *v17; i; i = (_QWORD *)*i )
            {
              if ( i == (_QWORD *)a3 )
                break;
              v17 = (_QWORD **)i;
            }
            *v17 = *(_QWORD **)a3;
          }
          **(_DWORD **)(a3 + 16) -= *(_DWORD *)(a3 + 36);
          v19 = *(_DWORD **)(a3 + 16);
          if ( !*v19 )
            LocalFree(v19);
          *(_QWORD *)(a3 + 56) = 0;
          *(_DWORD *)(a3 + 64) = 0;
          *(_QWORD *)(a3 + 72) = 0;
          LocalFree((HLOCAL)a3);
        }
      }
    }
    else
    {
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 )
        WPP_SF_d(v10[2], 276, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v11);
      v12 = *(_DWORD **)(a3 + 16);
      v13 = 0xFFFFFFFFLL;
      --*(_DWORD *)(a3 + 36);
      --*v12;
    }
    DavRevertToSelf(v13, v7, v8);
  }
  return v9;
}

```

## disassembly

```asm
0x180003cbc  mov     rax, rsp
0x180003cbf  mov     [rax+8], rbx
0x180003cc3  mov     [rax+18h], rbp
0x180003cc7  mov     [rax+10h], edx
0x180003cca  push    rsi
0x180003ccb  push    rdi
0x180003ccc  push    r14
0x180003cce  sub     rsp, 60h
0x180003cd2  xorps   xmm0, xmm0
0x180003cd5  mov     r14d, r9d
0x180003cd8  movups  xmmword ptr [rax-28h], xmm0
0x180003cdc  mov     rbx, r8
0x180003cdf  call    DavImpersonateClient
0x180003ce4  mov     esi, eax
0x180003ce6  test    eax, eax
0x180003ce8  jz      short loc_180003D28
0x180003cea  mov     rcx, cs:WPP_GLOBAL_Control
0x180003cf1  lea     rdi, WPP_GLOBAL_Control
0x180003cf8  cmp     rcx, rdi
0x180003cfb  jz      loc_180003F6D
0x180003d01  test    byte ptr [rcx+1Ch], 1
0x180003d05  jz      loc_180003F6D
0x180003d0b  mov     rcx, [rcx+10h]
0x180003d0f  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180003d16  mov     edx, 112h
0x180003d1b  mov     r9d, eax
0x180003d1e  call    WPP_SF_d
0x180003d23  jmp     loc_180003F6D
0x180003d28  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d2f  lea     rdi, WPP_GLOBAL_Control
0x180003d36  lea     rbp, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180003d3d  cmp     rcx, rdi
0x180003d40  jz      short loc_180003D68
0x180003d42  test    byte ptr [rcx+1Ch], 2
0x180003d46  jz      short loc_180003D68
0x180003d48  mov     r9d, [rsp+78h+arg_8]
0x180003d50  mov     edx, 113h
0x180003d55  mov     rcx, [rcx+10h]
0x180003d59  mov     r8, rbp
0x180003d5c  call    WPP_SF_d
0x180003d61  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d68  cmp     qword ptr [rbx+18h], 0
0x180003d6d  jnz     short loc_180003DB2
0x180003d6f  cmp     [rsp+78h+arg_8], 0
0x180003d77  jnz     short loc_180003DB2
0x180003d79  mov     r9d, [rbx+24h]
0x180003d7d  lea     eax, [r9-1]
0x180003d81  test    eax, eax
0x180003d83  jz      short loc_180003DB2
0x180003d85  cmp     rcx, rdi
0x180003d88  jz      short loc_180003DA1
0x180003d8a  test    byte ptr [rcx+1Ch], 2
0x180003d8e  jz      short loc_180003DA1
0x180003d90  mov     rcx, [rcx+10h]
0x180003d94  mov     edx, 114h
0x180003d99  mov     r8, rbp
0x180003d9c  call    WPP_SF_d
0x180003da1  mov     rax, [rbx+10h]
0x180003da5  or      ecx, 0FFFFFFFFh
0x180003da8  add     [rbx+24h], ecx
0x180003dab  add     [rax], ecx
0x180003dad  jmp     loc_180003F68
0x180003db2  mov     rcx, [rbx+28h]; FileHandle
0x180003db6  lea     rax, [rsp+78h+arg_8]
0x180003dbe  mov     [rsp+78h+OutputBufferLength], 0; OutputBufferLength
0x180003dc6  xor     r9d, r9d; ApcContext
0x180003dc9  mov     [rsp+78h+OutputBuffer], 0; OutputBuffer
0x180003dd2  xor     r8d, r8d; ApcRoutine
0x180003dd5  mov     [rsp+78h+InputBufferLength], 4; InputBufferLength
0x180003ddd  xor     edx, edx; Event
0x180003ddf  mov     [rsp+78h+InputBuffer], rax; InputBuffer
0x180003de4  lea     rax, [rsp+78h+var_28]
0x180003de9  mov     [rsp+78h+FsControlCode], 4000020h; FsControlCode
0x180003df1  mov     [rsp+78h+IoStatusBlock], rax; IoStatusBlock
0x180003df6  call    cs:__imp_NtFsControlFile
0x180003dfc  test    eax, eax
0x180003dfe  js      loc_180003F38
0x180003e04  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e0b  cmp     rcx, rdi
0x180003e0e  jz      short loc_180003E2B
0x180003e10  test    byte ptr [rcx+1Ch], 2
0x180003e14  jz      short loc_180003E2B
0x180003e16  mov     r9, [rbx+28h]
0x180003e1a  mov     edx, 116h
0x180003e1f  mov     rcx, [rcx+10h]
0x180003e23  mov     r8, rbp
0x180003e26  call    WPP_SF_q
0x180003e2b  mov     rcx, [rbx+28h]; Handle
0x180003e2f  call    cs:__imp_NtClose
0x180003e35  test    eax, eax
0x180003e37  jz      short loc_180003E5F
0x180003e39  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e40  cmp     rcx, rdi
0x180003e43  jz      short loc_180003E5F
0x180003e45  test    byte ptr [rcx+1Ch], 1
0x180003e49  jz      short loc_180003E5F
0x180003e4b  mov     rcx, [rcx+10h]
0x180003e4f  mov     edx, 117h
0x180003e54  mov     r9d, eax
0x180003e57  mov     r8, rbp
0x180003e5a  call    WPP_SF_d
0x180003e5f  mov     rcx, [rbx+50h]; hObject
0x180003e63  call    cs:__imp_CloseHandle
0x180003e69  mov     rdx, [rbx+30h]; lpTargetPath
0x180003e6d  or      r9, 0FFFFFFFFFFFFFFFFh; Token
0x180003e71  mov     rcx, [rbx+18h]; hMem
0x180003e75  xor     r8d, r8d; lpDeviceName
0x180003e78  mov     dword ptr [rsp+78h+IoStatusBlock], 1; int
0x180003e80  call    DavDeleteSymbolicLink
0x180003e85  mov     esi, eax
0x180003e87  test    eax, eax
0x180003e89  jz      short loc_180003EBE
0x180003e8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e92  cmp     rcx, rdi
0x180003e95  jz      loc_180003F68
0x180003e9b  test    byte ptr [rcx+1Ch], 1
0x180003e9f  jz      loc_180003F68
0x180003ea5  mov     rcx, [rcx+10h]
0x180003ea9  mov     edx, 118h
0x180003eae  mov     r9d, eax
0x180003eb1  mov     r8, rbp
0x180003eb4  call    WPP_SF_d
0x180003eb9  jmp     loc_180003F68
0x180003ebe  mov     r8, cs:DavUseObject
0x180003ec5  mov     rcx, r14
0x180003ec8  add     rcx, rcx
0x180003ecb  mov     rdx, [r8+rcx*8]
0x180003ecf  cmp     rdx, rbx
0x180003ed2  jz      short loc_180003EF7
0x180003ed4  mov     rcx, [rdx]
0x180003ed7  test    rcx, rcx
0x180003eda  jz      short loc_180003EEF
0x180003edc  cmp     rcx, rbx
0x180003edf  jz      short loc_180003EEF
0x180003ee1  mov     rax, [rcx]
0x180003ee4  mov     rdx, rcx
0x180003ee7  mov     rcx, rax
0x180003eea  test    rax, rax
0x180003eed  jnz     short loc_180003EDC
0x180003eef  mov     rax, [rbx]
0x180003ef2  mov     [rdx], rax
0x180003ef5  jmp     short loc_180003EFE
0x180003ef7  mov     rax, [rbx]
0x180003efa  mov     [r8+rcx*8], rax
0x180003efe  mov     rcx, [rbx+10h]
0x180003f02  mov     eax, [rbx+24h]
0x180003f05  sub     [rcx], eax
0x180003f07  mov     rcx, [rbx+10h]; hMem
0x180003f0b  cmp     dword ptr [rcx], 0
0x180003f0e  jnz     short loc_180003F16
0x180003f10  call    cs:__imp_LocalFree
0x180003f16  mov     rcx, rbx; hMem
0x180003f19  mov     qword ptr [rbx+38h], 0
0x180003f21  mov     dword ptr [rbx+40h], 0
0x180003f28  mov     qword ptr [rbx+48h], 0
0x180003f30  call    cs:__imp_LocalFree
0x180003f36  jmp     short loc_180003F68
0x180003f38  mov     ecx, eax; Status
0x180003f3a  call    cs:__imp_RtlNtStatusToDosError
0x180003f40  mov     esi, eax
0x180003f42  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f49  cmp     rcx, rdi
0x180003f4c  jz      short loc_180003F68
0x180003f4e  test    byte ptr [rcx+1Ch], 1
0x180003f52  jz      short loc_180003F68
0x180003f54  mov     rcx, [rcx+10h]
0x180003f58  mov     edx, 115h
0x180003f5d  mov     r9d, eax
0x180003f60  mov     r8, rbp
0x180003f63  call    WPP_SF_d
0x180003f68  call    DavRevertToSelf
0x180003f6d  lea     r11, [rsp+78h+var_18]
0x180003f72  mov     eax, esi
0x180003f74  mov     rbx, [r11+20h]
0x180003f78  mov     rbp, [r11+30h]
0x180003f7c  mov     rsp, r11
0x180003f7f  pop     r14
0x180003f81  pop     rdi
0x180003f82  pop     rsi
0x180003f83  retn
```
