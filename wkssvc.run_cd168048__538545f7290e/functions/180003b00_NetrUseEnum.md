# NetrUseEnum

- ea: `0x180003b00`
- end: `0x180003daa`
- name: `NetrUseEnum`
- size: `682`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002c20`
- `0x1800033c0`
- `0x180003b00`
- `0x180005504`
- `0x18001fbd0`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x180003c3f`
- `ntdll!RtlAcquireResourceShared` at `0x180003c3f`
- `ntdll!RtlCopyLuid` at `0x180003bd5`
- `ntdll!RtlCopyLuid` at `0x180003bd5`
- `ntdll!RtlReleaseResource` at `0x180003d08`
- `ntdll!RtlReleaseResource` at `0x180003d08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003cf5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003cf5`

## pseudocode

```c
__int64 __fastcall NetrUseEnum(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4, __int64 a5)
{
  __int64 v8; // rsi
  int v9; // r14d
  DWORD v10; // r15d
  int v11; // ecx
  __int64 v12; // rax
  __int64 result; // rax
  unsigned int v14; // ebx
  __int64 i; // rax
  __int64 v16; // rcx
  __int64 *v17; // r8
  unsigned int v18; // ebx
  struct _LUID SourceLuid; // [rsp+50h] [rbp-88h] BYREF
  __int64 v20; // [rsp+58h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-78h] BYREF
  __int64 v22; // [rsp+68h] [rbp-70h] BYREF
  __int64 v23; // [rsp+70h] [rbp-68h]
  struct _LUID DestinationLuid[2]; // [rsp+78h] [rbp-60h] BYREF
  __int128 v25; // [rsp+88h] [rbp-50h]
  int v26; // [rsp+98h] [rbp-40h]

  v23 = a5;
  SourceLuid = 0;
  *(_OWORD *)&DestinationLuid[0].LowPart = 0;
  v25 = 0;
  v26 = 0;
  hMem = 0;
  v8 = 0;
  v22 = 0;
  v9 = 0;
  LODWORD(v20) = 0;
  v10 = (unsigned __int16)*(_DWORD *)a2;
  if ( v10 > 3 )
    return 124;
  v11 = *(_DWORD *)a2 & 0x10000;
  v12 = *(_QWORD *)(a2 + 8);
  if ( !v12 )
    return 87;
  *(_QWORD *)(v12 + 8) = 0;
  **(_DWORD **)(a2 + 8) = 0;
  if ( v11 )
  {
    SourceLuid = (struct _LUID)-1LL;
  }
  else
  {
    result = WsImpersonateAndGetLogonId(&SourceLuid);
    if ( (_DWORD)result )
      return result;
  }
  DestinationLuid[0].LowPart = 1;
  DestinationLuid[0].HighPart = 6;
  RtlCopyLuid((PLUID)&DestinationLuid[1].HighPart, &SourceLuid);
  DestinationLuid[1].LowPart = v10;
  v26 = 0;
  result = WsDeviceControlGetInfo(0, WsRedirDeviceHandle, 1311143, DestinationLuid, 36, &hMem, -1, 0);
  if ( !(_DWORD)result )
  {
    v14 = DWORD2(v25);
    if ( RtlAcquireResourceShared(&Resource, 1u) )
    {
      for ( i = 0; (unsigned int)i < dword_180052110; i = (unsigned int)(i + 1) )
      {
        v16 = Use + 24 * i;
        if ( SourceLuid.LowPart == *(_DWORD *)(v16 + 8) && SourceLuid.HighPart == *(_DWORD *)(v16 + 12)
          || SourceLuid.LowPart == *(_DWORD *)(v16 + 16) && SourceLuid.HighPart == *(_DWORD *)(v16 + 20) )
        {
          v17 = *(__int64 **)v16;
          goto LABEL_14;
        }
      }
      v17 = 0;
LABEL_14:
      if ( v14 || v17 )
      {
        v18 = WsEnumUseInfo(
                &SourceLuid,
                v10,
                v17,
                (unsigned __int16 *)hMem,
                v14,
                (HLOCAL *)&v22,
                a3,
                &v20,
                a4,
                (int *)v23);
        v8 = v22;
        v9 = v20;
      }
      else
      {
        *a4 = 0;
        v18 = 0;
      }
    }
    else
    {
      v18 = 2140;
    }
    LocalFree(hMem);
    RtlReleaseResource(&Resource);
    *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8LL) = v8;
    **(_DWORD **)(a2 + 8) = v9;
    return v18;
  }
  return result;
}

```

## disassembly

```asm
0x180003b00  mov     r11, rsp
0x180003b03  mov     [r11+8], rbx
0x180003b07  mov     [r11+18h], rsi
0x180003b0b  push    rdi
0x180003b0c  push    r12
0x180003b0e  push    r13
0x180003b10  push    r14
0x180003b12  push    r15
0x180003b14  sub     rsp, 0B0h
0x180003b1b  mov     rax, cs:__security_cookie
0x180003b22  xor     rax, rsp
0x180003b25  mov     [rsp+0D8h+var_38], rax
0x180003b2d  mov     r12, r9
0x180003b30  mov     r13d, r8d
0x180003b33  mov     rdi, rdx
0x180003b36  mov     rax, [rsp+0D8h+arg_20]
0x180003b3e  mov     [rsp+0D8h+var_68], rax
0x180003b43  xor     ebx, ebx
0x180003b45  mov     qword ptr [rsp+0D8h+SourceLuid.LowPart], rbx
0x180003b4a  xorps   xmm0, xmm0
0x180003b4d  xor     eax, eax
0x180003b4f  movups  xmmword ptr [rsp+0D8h+DestinationLuid.LowPart], xmm0
0x180003b54  movups  xmmword ptr [r11-50h], xmm0
0x180003b59  mov     [r11-40h], eax
0x180003b5d  mov     [r11-78h], rbx
0x180003b61  mov     esi, ebx
0x180003b63  mov     [r11-70h], rbx
0x180003b67  mov     r14d, ebx
0x180003b6a  mov     dword ptr [rsp+0D8h+var_80], ebx
0x180003b6e  mov     ecx, [rdx]
0x180003b70  movzx   r15d, cx
0x180003b74  cmp     r15d, 3
0x180003b78  ja      loc_180003D99
0x180003b7e  and     ecx, 10000h
0x180003b84  mov     rax, [rdx+8]
0x180003b88  test    rax, rax
0x180003b8b  jz      loc_180003DA0
0x180003b91  mov     [rax+8], rbx
0x180003b95  mov     rax, [rdx+8]
0x180003b99  mov     [rax], ebx
0x180003b9b  jmp     short loc_180003BA7
0x180003b9d  mov     eax, 57h ; 'W'
0x180003ba2  jmp     loc_180003D25
0x180003ba7  test    ecx, ecx
0x180003ba9  jz      loc_180003D6C
0x180003baf  mov     qword ptr [rsp+0D8h+SourceLuid.LowPart], 0FFFFFFFFFFFFFFFFh
0x180003bb8  mov     [rsp+0D8h+DestinationLuid.LowPart], 1
0x180003bc0  mov     [rsp+0D8h+DestinationLuid.HighPart], 6
0x180003bc8  lea     rdx, [rsp+0D8h+SourceLuid]; SourceLuid
0x180003bcd  lea     rcx, [rsp+0D8h+DestinationLuid.HighPart+8]; DestinationLuid
0x180003bd5  call    cs:__imp_RtlCopyLuid
0x180003bdc  nop     dword ptr [rax+rax+00h]
0x180003be1  mov     [rsp+0D8h+DestinationLuid.LowPart+8], r15d
0x180003be9  mov     [rsp+0D8h+var_40], ebx
0x180003bf0  mov     dword ptr [rsp+0D8h+var_A0], ebx
0x180003bf4  mov     [rsp+0D8h+var_A8], 0FFFFFFFFh
0x180003bfc  lea     rax, [rsp+0D8h+hMem]
0x180003c01  mov     [rsp+0D8h+var_B0], rax
0x180003c06  mov     [rsp+0D8h+var_B8], 24h ; '$'
0x180003c0e  lea     r9, [rsp+0D8h+DestinationLuid]
0x180003c13  mov     r8d, 1401A7h
0x180003c19  mov     rdx, cs:WsRedirDeviceHandle
0x180003c20  xor     ecx, ecx
0x180003c22  call    WsDeviceControlGetInfo
0x180003c27  test    eax, eax
0x180003c29  jnz     loc_180003D25
0x180003c2f  mov     ebx, [rsp+0D8h+var_48]
0x180003c36  mov     dl, 1; Wait
0x180003c38  lea     rcx, Resource; Resource
0x180003c3f  call    cs:__imp_RtlAcquireResourceShared
0x180003c46  nop     dword ptr [rax+rax+00h]
0x180003c4b  test    al, al
0x180003c4d  jz      loc_180003D80
0x180003c53  xor     eax, eax
0x180003c55  mov     r11d, [rsp+0D8h+SourceLuid.HighPart]
0x180003c5a  mov     r9d, [rsp+0D8h+SourceLuid.LowPart]
0x180003c5f  mov     r8d, cs:dword_180052110
0x180003c66  mov     r10, cs:Use
0x180003c6d  nop     dword ptr [rax]
0x180003c70  cmp     eax, r8d
0x180003c73  jnb     loc_180003D64
0x180003c79  lea     rdx, [rax+rax*2]
0x180003c7d  lea     rcx, [r10+rdx*8]
0x180003c81  cmp     r9d, [rcx+8]
0x180003c85  jz      short loc_180003C95
0x180003c87  cmp     r9d, [rcx+10h]
0x180003c8b  jz      loc_180003D8A
0x180003c91  inc     eax
0x180003c93  jmp     short loc_180003C70
0x180003c95  cmp     r11d, [rcx+0Ch]
0x180003c99  jnz     short loc_180003C87
0x180003c9b  mov     r8, [rcx]
0x180003c9e  test    ebx, ebx
0x180003ca0  jz      loc_180003D53
0x180003ca6  mov     rax, [rsp+0D8h+var_68]
0x180003cab  mov     [rsp+0D8h+var_90], rax; __int64
0x180003cb0  mov     [rsp+0D8h+var_98], r12; __int64
0x180003cb5  lea     rax, [rsp+0D8h+var_80]
0x180003cba  mov     [rsp+0D8h+var_A0], rax; __int64
0x180003cbf  mov     [rsp+0D8h+var_A8], r13d; int
0x180003cc4  lea     rax, [rsp+0D8h+var_70]
0x180003cc9  mov     [rsp+0D8h+var_B0], rax; __int64
0x180003cce  mov     [rsp+0D8h+var_B8], ebx; int
0x180003cd2  mov     r9, [rsp+0D8h+hMem]
0x180003cd7  mov     edx, r15d
0x180003cda  lea     rcx, [rsp+0D8h+SourceLuid]; SourceLuid
0x180003cdf  call    WsEnumUseInfo
0x180003ce4  mov     ebx, eax
0x180003ce6  mov     rsi, [rsp+0D8h+var_70]
0x180003ceb  mov     r14d, dword ptr [rsp+0D8h+var_80]
0x180003cf0  mov     rcx, [rsp+0D8h+hMem]; hMem
0x180003cf5  call    cs:__imp_LocalFree
0x180003cfc  nop     dword ptr [rax+rax+00h]
0x180003d01  lea     rcx, Resource; Resource
0x180003d08  call    cs:__imp_RtlReleaseResource
0x180003d0f  nop     dword ptr [rax+rax+00h]
0x180003d14  mov     rcx, [rdi+8]
0x180003d18  mov     [rcx+8], rsi
0x180003d1c  mov     rcx, [rdi+8]
0x180003d20  mov     [rcx], r14d
0x180003d23  mov     eax, ebx
0x180003d25  mov     rcx, [rsp+0D8h+var_38]
0x180003d2d  xor     rcx, rsp; StackCookie
0x180003d30  call    __security_check_cookie
0x180003d35  lea     r11, [rsp+0D8h+var_28]
0x180003d3d  mov     rbx, [r11+30h]
0x180003d41  mov     rsi, [r11+40h]
0x180003d45  mov     rsp, r11
0x180003d48  pop     r15
0x180003d4a  pop     r14
0x180003d4c  pop     r13
0x180003d4e  pop     r12
0x180003d50  pop     rdi
0x180003d51  retn
0x180003d53  test    r8, r8
0x180003d56  jnz     loc_180003CA6
0x180003d5c  mov     [r12], r8d
0x180003d60  xor     ebx, ebx
0x180003d62  jmp     short loc_180003CF0
0x180003d64  xor     r8d, r8d
0x180003d67  jmp     loc_180003C9E
0x180003d6c  lea     rcx, [rsp+0D8h+SourceLuid]; DestinationLuid
0x180003d71  call    WsImpersonateAndGetLogonId
0x180003d76  test    eax, eax
0x180003d78  jz      loc_180003BB8
0x180003d7e  jmp     short loc_180003D25
0x180003d80  mov     ebx, 85Ch
0x180003d85  jmp     loc_180003CF0
0x180003d8a  cmp     r11d, [rcx+14h]
0x180003d8e  jnz     loc_180003C91
0x180003d94  jmp     loc_180003C9B
0x180003d99  mov     eax, 7Ch ; '|'
0x180003d9e  jmp     short loc_180003D25
0x180003da0  mov     eax, 57h ; 'W'
0x180003da5  jmp     loc_180003D25
```
