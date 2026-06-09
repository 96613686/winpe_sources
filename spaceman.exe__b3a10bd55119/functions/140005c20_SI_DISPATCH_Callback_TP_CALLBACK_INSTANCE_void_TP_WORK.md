# SI_DISPATCH::Callback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x140005c20`
- end: `0x140005cef`
- name: `?Callback@SI_DISPATCH@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `207`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, _QWORD *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140005c20`
- `0x14000c018`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005c83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005c83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005cc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005cc3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140005c3d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140005c3d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140005ce0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140005ce0`

## pseudocode

```c
void __fastcall SI_DISPATCH::Callback(PTP_CALLBACK_INSTANCE Instance, _QWORD *Context, PTP_WORK Work)
{
  __int128 *v3; // rbp
  void *v5; // rdx
  int v6; // esi
  signed __int64 v7; // rbx
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v11[20]; // [rsp+30h] [rbp-48h]
  int v12; // [rsp+44h] [rbp-34h]

  v3 = (__int128 *)Context[2];
  v5 = (void *)Context[7];
  v6 = 0;
  if ( v5 )
  {
    if ( SetThreadToken(0, v5) )
    {
      v6 = 1;
      goto LABEL_5;
    }
    return;
  }
  do
  {
LABEL_5:
    v7 = Context[6];
    if ( v7 == Context[1] )
      goto LABEL_12;
  }
  while ( v7 != _InterlockedCompareExchange64(Context + 6, *(_QWORD *)v7, v7) );
  *(_DWORD *)(v7 + 20) = 1;
  if ( *(_DWORD *)Context != 3 )
  {
    SetLastError(0x57u);
LABEL_10:
    *(_DWORD *)(v7 + 16) = GetLastError();
    *(_DWORD *)(v7 + 20) = 2;
    goto LABEL_12;
  }
  v8 = *v3;
  *(_OWORD *)v11 = v3[1];
  v9 = *(_OWORD *)(v7 + 56);
  v10 = v8;
  v12 = HIDWORD(*((_QWORD *)v3 + 4));
  *(_OWORD *)&v11[4] = v9;
  if ( !(unsigned int)SiRefreshDrive((struct _SP_REFRESH_INFO *)&v10, (struct _SU_DRIVE_OBJECT *)v7) )
    goto LABEL_10;
  *(_DWORD *)(v7 + 20) = 3;
LABEL_12:
  if ( v6 )
    RevertToSelf();
}

```

## disassembly

```asm
0x140005c20  push    rbx
0x140005c22  push    rbp
0x140005c23  push    rsi
0x140005c24  push    rdi
0x140005c25  sub     rsp, 58h
0x140005c29  mov     rbp, [rdx+10h]
0x140005c2d  mov     rdi, rdx
0x140005c30  mov     rdx, [rdx+38h]; Token
0x140005c34  xor     esi, esi
0x140005c36  test    rdx, rdx
0x140005c39  jz      short loc_140005C63
0x140005c3b  xor     ecx, ecx; Thread
0x140005c3d  call    cs:__imp_SetThreadToken
0x140005c43  test    eax, eax
0x140005c45  jz      loc_140005CE6
0x140005c4b  mov     esi, 1
0x140005c50  jmp     short loc_140005C63
0x140005c52  mov     rcx, [rbx]
0x140005c55  mov     rax, rbx
0x140005c58  lock cmpxchg [rdi+30h], rcx
0x140005c5e  cmp     rbx, rax
0x140005c61  jz      short loc_140005C72
0x140005c63  mov     rbx, [rdi+30h]
0x140005c67  mov     rax, [rdi+8]
0x140005c6b  cmp     rbx, rax
0x140005c6e  jnz     short loc_140005C52
0x140005c70  jmp     short loc_140005CDC
0x140005c72  mov     dword ptr [rbx+14h], 1
0x140005c79  cmp     dword ptr [rdi], 3
0x140005c7c  jz      short loc_140005C8B
0x140005c7e  mov     ecx, 57h ; 'W'; dwErrCode
0x140005c83  call    cs:__imp_SetLastError
0x140005c89  jmp     short loc_140005CC3
0x140005c8b  movups  xmm1, xmmword ptr [rbp+10h]
0x140005c8f  mov     rdx, rbx; struct _SU_DRIVE_OBJECT *
0x140005c92  lea     rcx, [rsp+78h+var_58]; struct _SP_REFRESH_INFO *
0x140005c97  movups  xmm0, xmmword ptr [rbp+0]
0x140005c9b  movups  [rsp+78h+var_48], xmm1
0x140005ca0  movups  xmm1, xmmword ptr [rbx+38h]
0x140005ca4  movups  [rsp+78h+var_58], xmm0
0x140005ca9  movsd   xmm0, qword ptr [rbp+20h]
0x140005cae  movsd   qword ptr [rsp+78h+var_38], xmm0
0x140005cb4  movdqu  [rsp+78h+var_48+4], xmm1
0x140005cba  call    ?SiRefreshDrive@@YAHPEAU_SP_REFRESH_INFO@@PEAU_SU_DRIVE_OBJECT@@H@Z; SiRefreshDrive(_SP_REFRESH_INFO *,_SU_DRIVE_OBJECT *,int)
0x140005cbf  test    eax, eax
0x140005cc1  jnz     short loc_140005CD5
0x140005cc3  call    cs:__imp_GetLastError
0x140005cc9  mov     [rbx+10h], eax
0x140005ccc  mov     dword ptr [rbx+14h], 2
0x140005cd3  jmp     short loc_140005CDC
0x140005cd5  mov     dword ptr [rbx+14h], 3
0x140005cdc  test    esi, esi
0x140005cde  jz      short loc_140005CE6
0x140005ce0  call    cs:__imp_RevertToSelf
0x140005ce6  add     rsp, 58h
0x140005cea  pop     rdi
0x140005ceb  pop     rsi
0x140005cec  pop     rbp
0x140005ced  pop     rbx
0x140005cee  retn
```
