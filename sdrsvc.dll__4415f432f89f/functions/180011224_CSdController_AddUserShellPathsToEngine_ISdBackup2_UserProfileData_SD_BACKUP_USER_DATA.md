# CSdController::_AddUserShellPathsToEngine(ISdBackup2 *,_UserProfileData *,_SD_BACKUP_USER_DATA *)

- ea: `0x180011224`
- end: `0x1800113e9`
- name: `?_AddUserShellPathsToEngine@CSdController@@AEAAJPEAUISdBackup2@@PEAU_UserProfileData@@PEAU_SD_BACKUP_USER_DATA@@@Z`
- size: `453`
- prototype: `__int64 __fastcall(CSdController *this, struct ISdBackup2 *, struct _UserProfileData *, struct _SD_BACKUP_USER_DATA *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800106f4`

## callees

- `0x180010980`
- `0x180011224`
- `0x18001586c`
- `0x180015974`
- `0x180018f6c`
- `0x18001fc5c`
- `0x180020488`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011321`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800113bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011321`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800113bb`

## string_xrefs

- `0x18001124c`: `CSdController::_AddUserShellPathsToEngine`

## pseudocode

```c
__int64 __fastcall CSdController::_AddUserShellPathsToEngine(
        CSdController *this,
        struct ISdBackup2 *a2,
        struct _UserProfileData *a3,
        struct _SD_BACKUP_USER_DATA *a4)
{
  unsigned __int16 *v7; // r14
  __int16 v8; // ax
  int v9; // ebx
  __int64 v10; // rsi
  const unsigned __int16 *v11; // r15
  int ShellPath; // eax
  bool v13; // sf
  unsigned int v14; // ebx
  _QWORD v16[2]; // [rsp+20h] [rbp-58h] BYREF
  int v17; // [rsp+30h] [rbp-48h] BYREF
  __int16 v18; // [rsp+34h] [rbp-44h]
  __int16 v19; // [rsp+36h] [rbp-42h]
  unsigned __int16 *v20; // [rsp+C0h] [rbp+48h] BYREF

  v20 = (unsigned __int16 *)this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "CSdController::_AddUserShellPathsToEngine", 889, 0);
  v7 = 0;
  v16[0] = qword_180028260;
  v8 = 896;
  v16[1] = 0;
  if ( a2 && (v18 = 896, v8 = 897, a3) )
  {
    v17 = 0;
    v9 = 255;
    v18 = 897;
    if ( a4 )
      v9 = *((_DWORD *)a4 + 6) ^ 0xFF;
    v10 = 0;
    do
    {
      if ( (v9 & qword_18002D200[5 * v10]) != 0 )
      {
        if ( LODWORD(qword_18002D200[5 * v10]) == 16 )
        {
          v17 = CSdController::_AddAppDataPathsToEngine((CSdController *)qword_18002D200, a2, a3);
          if ( v17 < 0 )
          {
            v19 = 914;
            goto LABEL_24;
          }
          v18 = 914;
        }
        else
        {
          if ( LODWORD(qword_18002D200[5 * v10 + 4]) )
          {
            v11 = (const unsigned __int16 *)qword_18002D200[5 * v10 + 3];
          }
          else
          {
            v17 = CBsString::Set((CBsString *)v16, (const struct _GUID *)((char *)&qword_18002D200[5 * v10] + 4));
            v8 = 924;
            if ( v17 < 0 )
              goto LABEL_23;
            v11 = (const unsigned __int16 *)v16[0];
            v18 = 924;
          }
          CoTaskMemFree(v7);
          v20 = 0;
          ShellPath = GetShellPath(a3, v11, &v20);
          v7 = v20;
          v13 = ShellPath < 0;
          v17 = ShellPath;
          v8 = 930;
          if ( v13 )
            goto LABEL_23;
          v18 = 930;
          v17 = (*(__int64 (__fastcall **)(struct ISdBackup2 *, unsigned __int16 *, __int64))(*(_QWORD *)a2 + 32LL))(
                  a2,
                  v20,
                  3221225839LL);
          v8 = 931;
          if ( v17 < 0 )
            goto LABEL_23;
          v18 = 931;
        }
        v9 ^= LODWORD(qword_18002D200[5 * v10]);
      }
      v10 = (unsigned int)(v10 + 1);
    }
    while ( (unsigned int)v10 < 8 );
    v8 = 938;
    if ( v9 )
      goto LABEL_22;
    v17 = 0;
    v18 = 938;
  }
  else
  {
LABEL_22:
    v17 = -2147024809;
LABEL_23:
    v19 = v8;
  }
LABEL_24:
  CoTaskMemFree(v7);
  v14 = v17;
  CBsString::_Release((CBsString *)v16);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return v14;
}

```

## disassembly

```asm
0x180011224  mov     [rsp-40h+arg_0], rcx
0x180011229  push    rbp
0x18001122a  push    rbx
0x18001122b  push    rsi
0x18001122c  push    rdi
0x18001122d  push    r12
0x18001122f  push    r13
0x180011231  push    r14
0x180011233  push    r15
0x180011235  mov     rbp, rsp
0x180011238  sub     rsp, 78h
0x18001123c  mov     rdi, r9
0x18001123f  lea     rcx, [rbp+var_48]; this
0x180011243  mov     r12, r8
0x180011246  mov     r13, rdx
0x180011249  xor     r9d, r9d; unsigned __int16
0x18001124c  lea     rdx, aCsdcontrollerA_4; "CSdController::_AddUserShellPathsToEngi"...
0x180011253  mov     r8d, 379h; unsigned __int16
0x180011259  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001125e  lea     rax, qword_180028260
0x180011265  xor     r14d, r14d
0x180011268  mov     [rbp+var_58], rax
0x18001126c  mov     eax, 380h
0x180011271  mov     [rbp+var_50], r14
0x180011275  test    r13, r13
0x180011278  jz      loc_1800113AD
0x18001127e  mov     [rbp+var_44], ax
0x180011282  mov     eax, 381h
0x180011287  test    r12, r12
0x18001128a  jz      loc_1800113AD
0x180011290  mov     [rbp+var_48], r14d
0x180011294  mov     ebx, 0FFh
0x180011299  mov     [rbp+var_44], ax
0x18001129d  test    rdi, rdi
0x1800112a0  jz      short loc_1800112A5
0x1800112a2  xor     ebx, [rdi+18h]
0x1800112a5  xor     esi, esi
0x1800112a7  lea     rcx, qword_18002D200; this
0x1800112ae  mov     r15d, 392h
0x1800112b4  lea     rdi, [rsi+rsi*4]
0x1800112b8  test    [rcx+rdi*8], ebx
0x1800112bb  jz      loc_180011389
0x1800112c1  cmp     dword ptr [rcx+rdi*8], 10h
0x1800112c5  jnz     short loc_1800112E7
0x1800112c7  mov     r8, r12; struct _UserProfileData *
0x1800112ca  mov     rdx, r13; struct ISdBackup2 *
0x1800112cd  call    ?_AddAppDataPathsToEngine@CSdController@@AEAAJPEAUISdBackup2@@PEAU_UserProfileData@@@Z; CSdController::_AddAppDataPathsToEngine(ISdBackup2 *,_UserProfileData *)
0x1800112d2  mov     [rbp+var_48], eax
0x1800112d5  test    eax, eax
0x1800112d7  js      loc_1800113A6
0x1800112dd  mov     [rbp+var_44], r15w
0x1800112e2  jmp     loc_18001137F
0x1800112e7  cmp     dword ptr [rcx+rdi*8+20h], 0
0x1800112ec  jz      short loc_1800112F5
0x1800112ee  mov     r15, [rcx+rdi*8+18h]
0x1800112f3  jmp     short loc_18001131E
0x1800112f5  lea     rdx, [rcx+4]
0x1800112f9  lea     rdx, [rdx+rdi*8]; struct _GUID *
0x1800112fd  lea     rcx, [rbp+var_58]; this
0x180011301  call    ?Set@CBsString@@QEAAJAEBU_GUID@@@Z; CBsString::Set(_GUID const &)
0x180011306  mov     [rbp+var_48], eax
0x180011309  test    eax, eax
0x18001130b  mov     eax, 39Ch
0x180011310  js      loc_1800113B4
0x180011316  mov     r15, [rbp+var_58]
0x18001131a  mov     [rbp+var_44], ax
0x18001131e  mov     rcx, r14; pv
0x180011321  call    cs:__imp_CoTaskMemFree
0x180011327  lea     r8, [rbp+arg_0]; unsigned __int16 **
0x18001132b  mov     [rbp+arg_0], 0
0x180011333  mov     rdx, r15; unsigned __int16 *
0x180011336  mov     rcx, r12; struct _UserProfileData *
0x180011339  call    ?GetShellPath@@YAJPEAU_UserProfileData@@PEBGPEAPEAG@Z; GetShellPath(_UserProfileData *,ushort const *,ushort * *)
0x18001133e  mov     r14, [rbp+arg_0]
0x180011342  test    eax, eax
0x180011344  mov     [rbp+var_48], eax
0x180011347  mov     eax, 3A2h
0x18001134c  js      short loc_1800113B4
0x18001134e  mov     [rbp+var_44], ax
0x180011352  mov     r8d, 0C000016Fh
0x180011358  mov     rax, [r13+0]
0x18001135c  mov     rdx, r14
0x18001135f  mov     rcx, r13
0x180011362  mov     rax, [rax+20h]
0x180011366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001136b  mov     [rbp+var_48], eax
0x18001136e  test    eax, eax
0x180011370  mov     eax, 3A3h
0x180011375  js      short loc_1800113B4
0x180011377  mov     [rbp+var_44], ax
0x18001137b  lea     r15d, [rax-11h]
0x18001137f  lea     rcx, qword_18002D200
0x180011386  xor     ebx, [rcx+rdi*8]
0x180011389  inc     esi
0x18001138b  cmp     esi, 8
0x18001138e  jb      loc_1800112B4
0x180011394  mov     eax, 3AAh
0x180011399  test    ebx, ebx
0x18001139b  jnz     short loc_1800113AD
0x18001139d  mov     [rbp+var_48], ebx
0x1800113a0  mov     [rbp+var_44], ax
0x1800113a4  jmp     short loc_1800113B8
0x1800113a6  mov     [rbp+var_42], r15w
0x1800113ab  jmp     short loc_1800113B8
0x1800113ad  mov     [rbp+var_48], 80070057h
0x1800113b4  mov     [rbp+var_42], ax
0x1800113b8  mov     rcx, r14; pv
0x1800113bb  call    cs:__imp_CoTaskMemFree
0x1800113c1  mov     ebx, [rbp+var_48]
0x1800113c4  lea     rcx, [rbp+var_58]; this
0x1800113c8  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800113cd  lea     rcx, [rbp+var_48]; this
0x1800113d1  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800113d6  mov     eax, ebx
0x1800113d8  add     rsp, 78h
0x1800113dc  pop     r15
0x1800113de  pop     r14
0x1800113e0  pop     r13
0x1800113e2  pop     r12
0x1800113e4  pop     rdi
0x1800113e5  pop     rsi
0x1800113e6  pop     rbx
0x1800113e7  pop     rbp
0x1800113e8  retn
```
