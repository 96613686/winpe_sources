# GetAutogenKeysSingleThread(uchar *)

- ea: `0x180045e38`
- end: `0x180045f71`
- name: `?GetAutogenKeysSingleThread@@YAJPEAE@Z`
- size: `313`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180045ccc`

## callees

- `0x180045ab4`
- `0x180045e38`
- `0x180046a40`
- `0x18004741c`
- `0x1800478d8`
- `0x18004bf5f`
- `0x18004d350`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180045f59`
- `KERNEL32!CloseHandle` at `0x180045f59`
- `KERNEL32!WaitForSingleObject` at `0x180045f0f`
- `KERNEL32!WaitForSingleObject` at `0x180045f0f`
- `KERNEL32!SetEvent` at `0x180045f50`
- `KERNEL32!SetEvent` at `0x180045f50`
- `KERNEL32!CreateEventW` at `0x180045ef2`
- `KERNEL32!CreateEventW` at `0x180045ef2`

## pseudocode

```c
__int64 __fastcall GetAutogenKeysSingleThread(unsigned __int8 *a1)
{
  __int64 v2; // rdi
  unsigned int KeyFromHKCURegistry; // ebx
  __int64 v4; // rcx
  unsigned __int8 near **v5; // rax
  __int128 v6; // xmm1
  HANDLE EventW; // rax
  unsigned int LastWin32Error; // eax
  LSA_HANDLE ObjectHandle; // [rsp+38h] [rbp+10h] BYREF

  ObjectHandle = 0;
  v2 = -1;
  if ( (unsigned int)OpenLSAPolicy(&ObjectHandle) )
  {
    KeyFromHKCURegistry = GetKeyFromHKCURegistry(a1, 0x400u);
    if ( !KeyFromHKCURegistry )
    {
      v4 = 8;
      v5 = &g_pAutogenKey;
      do
      {
        *(_OWORD *)v5 = *(_OWORD *)a1;
        *((_OWORD *)v5 + 1) = *((_OWORD *)a1 + 1);
        *((_OWORD *)v5 + 2) = *((_OWORD *)a1 + 2);
        *((_OWORD *)v5 + 3) = *((_OWORD *)a1 + 3);
        *((_OWORD *)v5 + 4) = *((_OWORD *)a1 + 4);
        *((_OWORD *)v5 + 5) = *((_OWORD *)a1 + 5);
        *((_OWORD *)v5 + 6) = *((_OWORD *)a1 + 6);
        v5 += 16;
        v6 = *((_OWORD *)a1 + 7);
        a1 += 128;
        *((_OWORD *)v5 - 1) = v6;
        --v4;
      }
      while ( v4 );
    }
  }
  else
  {
    KeyFromHKCURegistry = DoesKeyExist(ObjectHandle);
    if ( !KeyFromHKCURegistry )
      goto LABEL_12;
    EventW = CreateEventW(0, 1, 1, L"ASP.NETAutoGenKeys4.0.30319.0Event");
    v2 = (__int64)EventW;
    if ( EventW )
    {
      WaitForSingleObject(EventW, 0x7530u);
      KeyFromHKCURegistry = DoesKeyExist(ObjectHandle);
      if ( !KeyFromHKCURegistry )
        goto LABEL_12;
      LastWin32Error = StoreKeyInLSA(ObjectHandle, a1);
    }
    else
    {
      LastWin32Error = GetLastWin32Error();
    }
    KeyFromHKCURegistry = LastWin32Error;
  }
LABEL_12:
  if ( ObjectHandle )
    LsaClose_0(ObjectHandle);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    SetEvent((HANDLE)v2);
    CloseHandle((HANDLE)v2);
  }
  return KeyFromHKCURegistry;
}

```

## disassembly

```asm
0x180045e38  mov     rax, rsp
0x180045e3b  mov     [rax+8], rbx
0x180045e3f  mov     [rax+18h], rsi
0x180045e43  push    rdi
0x180045e44  sub     rsp, 20h
0x180045e48  and     qword ptr [rax+10h], 0
0x180045e4d  mov     rsi, rcx
0x180045e50  lea     rcx, [rax+10h]; PolicyHandle
0x180045e54  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180045e58  call    ?OpenLSAPolicy@@YAJPEAPEAX@Z; OpenLSAPolicy(void * *)
0x180045e5d  test    eax, eax
0x180045e5f  jz      short loc_180045ED1
0x180045e61  mov     edx, 400h; Size
0x180045e66  mov     rcx, rsi; unsigned __int8 *
0x180045e69  call    ?GetKeyFromHKCURegistry@@YAJPEAEK@Z; GetKeyFromHKCURegistry(uchar *,ulong)
0x180045e6e  mov     ebx, eax
0x180045e70  test    eax, eax
0x180045e72  jnz     loc_180045F34
0x180045e78  lea     ecx, [rdi+9]
0x180045e7b  lea     edx, [rcx+78h]
0x180045e7e  lea     rax, ?g_pAutogenKey@@3PAEA; uchar near * g_pAutogenKey
0x180045e85  movups  xmm0, xmmword ptr [rsi]
0x180045e88  movups  xmmword ptr [rax], xmm0
0x180045e8b  movups  xmm1, xmmword ptr [rsi+10h]
0x180045e8f  movups  xmmword ptr [rax+10h], xmm1
0x180045e93  movups  xmm0, xmmword ptr [rsi+20h]
0x180045e97  movups  xmmword ptr [rax+20h], xmm0
0x180045e9b  movups  xmm1, xmmword ptr [rsi+30h]
0x180045e9f  movups  xmmword ptr [rax+30h], xmm1
0x180045ea3  movups  xmm0, xmmword ptr [rsi+40h]
0x180045ea7  movups  xmmword ptr [rax+40h], xmm0
0x180045eab  movups  xmm1, xmmword ptr [rsi+50h]
0x180045eaf  movups  xmmword ptr [rax+50h], xmm1
0x180045eb3  movups  xmm0, xmmword ptr [rsi+60h]
0x180045eb7  movups  xmmword ptr [rax+60h], xmm0
0x180045ebb  add     rax, rdx
0x180045ebe  movups  xmm1, xmmword ptr [rsi+70h]
0x180045ec2  add     rsi, rdx
0x180045ec5  movups  xmmword ptr [rax-10h], xmm1
0x180045ec9  sub     rcx, 1
0x180045ecd  jnz     short loc_180045E85
0x180045ecf  jmp     short loc_180045F34
0x180045ed1  mov     rcx, [rsp+28h+ObjectHandle]; PolicyHandle
0x180045ed6  call    ?DoesKeyExist@@YAJPEAX@Z; DoesKeyExist(void *)
0x180045edb  mov     ebx, eax
0x180045edd  test    eax, eax
0x180045edf  jz      short loc_180045F34
0x180045ee1  mov     edx, 1; bManualReset
0x180045ee6  lea     r9, aAspNetautogenk; "ASP.NETAutoGenKeys4.0.30319.0Event"
0x180045eed  mov     r8d, edx; bInitialState
0x180045ef0  xor     ecx, ecx; lpEventAttributes
0x180045ef2  call    cs:__imp_CreateEventW
0x180045ef8  mov     rdi, rax
0x180045efb  test    rax, rax
0x180045efe  jnz     short loc_180045F07
0x180045f00  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180045f05  jmp     short loc_180045F32
0x180045f07  mov     edx, 7530h; dwMilliseconds
0x180045f0c  mov     rcx, rax; hHandle
0x180045f0f  call    cs:__imp_WaitForSingleObject
0x180045f15  mov     rcx, [rsp+28h+ObjectHandle]; PolicyHandle
0x180045f1a  call    ?DoesKeyExist@@YAJPEAX@Z; DoesKeyExist(void *)
0x180045f1f  mov     ebx, eax
0x180045f21  test    eax, eax
0x180045f23  jz      short loc_180045F34
0x180045f25  mov     rcx, [rsp+28h+ObjectHandle]; PolicyHandle
0x180045f2a  mov     rdx, rsi; unsigned __int8 *
0x180045f2d  call    ?StoreKeyInLSA@@YAJPEAXPEAE@Z; StoreKeyInLSA(void *,uchar *)
0x180045f32  mov     ebx, eax
0x180045f34  mov     rcx, [rsp+28h+ObjectHandle]; ObjectHandle
0x180045f39  test    rcx, rcx
0x180045f3c  jz      short loc_180045F43
0x180045f3e  call    LsaClose_0
0x180045f43  lea     rax, [rdi-1]
0x180045f47  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180045f4b  ja      short loc_180045F5F
0x180045f4d  mov     rcx, rdi; hEvent
0x180045f50  call    cs:__imp_SetEvent
0x180045f56  mov     rcx, rdi; hObject
0x180045f59  call    cs:__imp_CloseHandle
0x180045f5f  mov     rsi, [rsp+28h+arg_10]
0x180045f64  mov     eax, ebx
0x180045f66  mov     rbx, [rsp+28h+arg_0]
0x180045f6b  add     rsp, 20h
0x180045f6f  pop     rdi
0x180045f70  retn
```
