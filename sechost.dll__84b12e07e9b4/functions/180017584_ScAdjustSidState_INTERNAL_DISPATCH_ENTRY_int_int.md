# ScAdjustSidState(_INTERNAL_DISPATCH_ENTRY *,int,int *)

- ea: `0x180017584`
- end: `0x1800176d4`
- name: `?ScAdjustSidState@@YAKPEAU_INTERNAL_DISPATCH_ENTRY@@HPEAH@Z`
- size: `336`
- prototype: `unsigned int __fastcall(struct _INTERNAL_DISPATCH_ENTRY *, int, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000bfb0`
- `0x180012840`

## callees

- `0x180017584`
- `0x180018dd8`
- `0x18004fa50`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800175f8`
- `ntdll!RtlNtStatusToDosError` at `0x180017622`
- `ntdll!RtlNtStatusToDosError` at `0x1800175f8`
- `ntdll!RtlNtStatusToDosError` at `0x180017622`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017680`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017680`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800176a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800176a6`
- `api-ms-win-security-base-l1-1-0!AdjustTokenGroups` at `0x180017676`
- `api-ms-win-security-base-l1-1-0!AdjustTokenGroups` at `0x180017676`

## pseudocode

```c
__int64 __fastcall ScAdjustSidState(struct _INTERNAL_DISPATCH_ENTRY *a1, int a2, int *a3)
{
  DWORD v3; // esi
  DWORD LastError; // edi
  NTSTATUS ServiceSidFromString; // eax
  const WCHAR *v9; // rcx
  NTSTATUS v10; // eax
  __int64 v11; // rbx
  __int64 v12; // rdx
  HLOCAL v13; // rax
  __int64 v14; // rcx
  HLOCAL v15; // rcx
  HLOCAL hMem[2]; // [rsp+30h] [rbp-40h] BYREF
  struct _TOKEN_GROUPS NewState; // [rsp+40h] [rbp-30h] BYREF
  __int128 v19; // [rsp+58h] [rbp-18h]

  v3 = 0;
  LastError = 0;
  memset(&NewState, 0, sizeof(NewState));
  *(_OWORD *)hMem = 0;
  v19 = 0;
  if ( !TokenHandle || !a1 || (*((_BYTE *)a1 + 56) & 8) == 0 )
    goto LABEL_16;
  ServiceSidFromString = ScCreateServiceSidFromString(*((PCWSTR *)a1 + 2), hMem);
  if ( ServiceSidFromString < 0 )
    return RtlNtStatusToDosError(ServiceSidFromString);
  v9 = (const WCHAR *)*((_QWORD *)a1 + 3);
  v3 = 1;
  if ( !v9 )
  {
LABEL_10:
    NewState.GroupCount = v3;
    v12 = 0;
    do
    {
      v13 = hMem[v12];
      v14 = (unsigned int)v12;
      v12 = (unsigned int)(v12 + 1);
      v14 *= 2;
      *((_QWORD *)&NewState.Groups[0].Sid + v14) = v13;
      *(&NewState.Groups[0].Attributes + 2 * v14) = a2 != 0 ? 4 : 0;
    }
    while ( (unsigned int)v12 < v3 );
    if ( AdjustTokenGroups(TokenHandle, 0, &NewState, 0, 0, 0) )
    {
      if ( a3 )
        *a3 = 1;
    }
    else
    {
      LastError = GetLastError();
    }
LABEL_16:
    v11 = 0;
    if ( !v3 )
      return LastError;
    goto LABEL_17;
  }
  v10 = ScCreateServiceSidFromString(v9, &hMem[1]);
  if ( v10 >= 0 )
  {
    v3 = 2;
    goto LABEL_10;
  }
  LastError = RtlNtStatusToDosError(v10);
  v11 = 0;
  do
  {
LABEL_17:
    v15 = hMem[v11];
    if ( v15 )
      LocalFree(v15);
    v11 = (unsigned int)(v11 + 1);
  }
  while ( (unsigned int)v11 < v3 );
  return LastError;
}

```

## disassembly

```asm
0x180017584  mov     [rsp-28h+arg_8], rbx
0x180017589  push    rbp
0x18001758a  push    rsi
0x18001758b  push    rdi
0x18001758c  push    r14
0x18001758e  push    r15
0x180017590  mov     rbp, rsp
0x180017593  sub     rsp, 70h
0x180017597  mov     rax, cs:__security_cookie
0x18001759e  xor     rax, rsp
0x1800175a1  mov     [rbp+var_8], rax
0x1800175a5  xorps   xmm0, xmm0
0x1800175a8  xor     esi, esi
0x1800175aa  xor     edi, edi
0x1800175ac  mov     qword ptr [rbp+NewState.GroupCount], rsi
0x1800175b0  cmp     cs:TokenHandle, rsi
0x1800175b7  mov     r14, r8
0x1800175ba  mov     r15d, edx
0x1800175bd  mov     rbx, rcx
0x1800175c0  movups  xmmword ptr [rbp+hMem], xmm0
0x1800175c4  movups  xmmword ptr [rbp+NewState.Groups.Sid], xmm0
0x1800175c8  movups  [rbp+var_18], xmm0
0x1800175cc  jz      loc_180017696
0x1800175d2  test    rcx, rcx
0x1800175d5  jz      loc_180017696
0x1800175db  test    byte ptr [rcx+38h], 8
0x1800175df  jz      loc_180017696
0x1800175e5  mov     rcx, [rcx+10h]; SourceString
0x1800175e9  lea     rdx, [rbp+hMem]
0x1800175ed  call    ScCreateServiceSidFromString
0x1800175f2  test    eax, eax
0x1800175f4  jns     short loc_180017605
0x1800175f6  mov     ecx, eax; Status
0x1800175f8  call    cs:__imp_RtlNtStatusToDosError
0x1800175fe  mov     edi, eax
0x180017600  jmp     loc_1800176B2
0x180017605  mov     rcx, [rbx+18h]; SourceString
0x180017609  mov     esi, 1
0x18001760e  test    rcx, rcx
0x180017611  jz      short loc_180017633
0x180017613  lea     rdx, [rbp+hMem+8]
0x180017617  call    ScCreateServiceSidFromString
0x18001761c  test    eax, eax
0x18001761e  jns     short loc_18001762E
0x180017620  mov     ecx, eax; Status
0x180017622  call    cs:__imp_RtlNtStatusToDosError
0x180017628  mov     edi, eax
0x18001762a  xor     ebx, ebx
0x18001762c  jmp     short loc_18001769C
0x18001762e  mov     esi, 2
0x180017633  neg     r15d
0x180017636  mov     [rbp+NewState.GroupCount], esi
0x180017639  sbb     r8d, r8d
0x18001763c  and     r8d, 4
0x180017640  xor     edx, edx
0x180017642  mov     rax, [rbp+rdx*8+hMem]
0x180017647  mov     ecx, edx
0x180017649  inc     edx
0x18001764b  add     rcx, rcx
0x18001764e  mov     [rbp+rcx*8+NewState.Groups.Sid], rax
0x180017653  mov     [rbp+rcx*8+NewState.Groups.Attributes], r8d
0x180017658  cmp     edx, esi
0x18001765a  jb      short loc_180017642
0x18001765c  mov     rcx, cs:TokenHandle; TokenHandle
0x180017663  lea     r8, [rbp+NewState]; NewState
0x180017667  mov     [rsp+70h+ReturnLength], rdi; ReturnLength
0x18001766c  xor     r9d, r9d; BufferLength
0x18001766f  xor     edx, edx; ResetToDefault
0x180017671  mov     [rsp+70h+PreviousState], rdi; PreviousState
0x180017676  call    cs:__imp_AdjustTokenGroups
0x18001767c  test    eax, eax
0x18001767e  jnz     short loc_18001768A
0x180017680  call    cs:__imp_GetLastError
0x180017686  mov     edi, eax
0x180017688  jmp     short loc_180017696
0x18001768a  test    r14, r14
0x18001768d  jz      short loc_180017696
0x18001768f  mov     dword ptr [r14], 1
0x180017696  xor     ebx, ebx
0x180017698  test    esi, esi
0x18001769a  jz      short loc_1800176B2
0x18001769c  mov     rcx, [rbp+rbx*8+hMem]; hMem
0x1800176a1  test    rcx, rcx
0x1800176a4  jz      short loc_1800176AC
0x1800176a6  call    cs:__imp_LocalFree
0x1800176ac  inc     ebx
0x1800176ae  cmp     ebx, esi
0x1800176b0  jb      short loc_18001769C
0x1800176b2  mov     eax, edi
0x1800176b4  mov     rcx, [rbp+var_8]
0x1800176b8  xor     rcx, rsp; StackCookie
0x1800176bb  call    __security_check_cookie
0x1800176c0  mov     rbx, [rsp+70h+arg_8]
0x1800176c8  add     rsp, 70h
0x1800176cc  pop     r15
0x1800176ce  pop     r14
0x1800176d0  pop     rdi
0x1800176d1  pop     rsi
0x1800176d2  pop     rbp
0x1800176d3  retn
```
