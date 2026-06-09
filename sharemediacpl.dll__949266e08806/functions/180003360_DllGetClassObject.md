# DllGetClassObject

- ea: `0x180003360`
- end: `0x180003456`
- name: `DllGetClassObject`
- size: `246`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003254`
- `0x180003360`
- `0x180003888`
- `0x1800038c8`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  unsigned int v6; // edi
  __int64 (__fastcall ***v7)(CClassFactory *__hidden, const struct _GUID *, void **); // rbx
  __int64 (__fastcall **v8)(CClassFactory *__hidden, const struct _GUID *, void **); // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF__guid__guid_q(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)riid, (_DWORD)ppv, (_DWORD)rclsid, (__int64)riid);
  *ppv = 0;
  v6 = -2147221231;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IClassFactory.Data1
    && *(_QWORD *)riid->Data4 == *(_QWORD *)IID_IClassFactory.Data4
    || *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IUnknown.Data1
    && *(_QWORD *)riid->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    v7 = &off_18001F030;
    if ( &CLSID_ShareMediaCplElementProvider )
    {
      do
      {
        v8 = v7[1];
        if ( *(__int64 (__fastcall **)(CClassFactory *__hidden, const struct _GUID *, void **))&rclsid->Data1 == *v8
          && *(__int64 (__fastcall **)(CClassFactory *__hidden, const struct _GUID *, void **))rclsid->Data4 == v8[1] )
        {
          *ppv = v7;
          DllAddRef();
          v6 = 0;
        }
        v7 += 7;
      }
      while ( v7[1] );
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_6dd76389fe1d31293452cff392e3d361_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180003360  push    rbx
0x180003362  push    rsi
0x180003363  push    rdi
0x180003364  push    r14
0x180003366  push    r15
0x180003368  sub     rsp, 30h
0x18000336c  mov     rsi, r8
0x18000336f  mov     rbx, rdx
0x180003372  mov     r14, rcx
0x180003375  mov     rcx, cs:WPP_GLOBAL_Control
0x18000337c  lea     r15, WPP_GLOBAL_Control
0x180003383  cmp     rcx, r15
0x180003386  jz      short loc_1800033A4
0x180003388  test    byte ptr [rcx+1Ch], 20h
0x18000338c  jz      short loc_1800033A4
0x18000338e  mov     rcx, [rcx+10h]
0x180003392  mov     r9, r14
0x180003395  mov     [rsp+58h+var_30], r8
0x18000339a  mov     [rsp+58h+var_38], rdx
0x18000339f  call    WPP_SF__guid__guid_q
0x1800033a4  mov     qword ptr [rsi], 0
0x1800033ab  mov     edi, 80040111h
0x1800033b0  mov     rax, [rbx]
0x1800033b3  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x1800033ba  jnz     short loc_1800033C9
0x1800033bc  mov     rax, [rbx+8]
0x1800033c0  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x1800033c7  jz      short loc_1800033E2
0x1800033c9  mov     rax, [rbx]
0x1800033cc  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800033d3  jnz     short loc_18000341E
0x1800033d5  mov     rax, [rbx+8]
0x1800033d9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800033e0  jnz     short loc_18000341E
0x1800033e2  cmp     cs:off_18001F038, 0
0x1800033ea  lea     rbx, off_18001F030
0x1800033f1  jz      short loc_18000341E
0x1800033f3  mov     rcx, [rbx+8]
0x1800033f7  mov     rax, [r14]
0x1800033fa  cmp     rax, [rcx]
0x1800033fd  jnz     short loc_180003413
0x1800033ff  mov     rax, [r14+8]
0x180003403  cmp     rax, [rcx+8]
0x180003407  jnz     short loc_180003413
0x180003409  mov     [rsi], rbx
0x18000340c  call    DllAddRef
0x180003411  xor     edi, edi
0x180003413  add     rbx, 38h ; '8'
0x180003417  cmp     qword ptr [rbx+8], 0
0x18000341c  jnz     short loc_1800033F3
0x18000341e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003425  cmp     rcx, r15
0x180003428  jz      short loc_180003448
0x18000342a  test    byte ptr [rcx+1Ch], 20h
0x18000342e  jz      short loc_180003448
0x180003430  mov     rcx, [rcx+10h]
0x180003434  lea     r8, WPP_6dd76389fe1d31293452cff392e3d361_Traceguids
0x18000343b  mov     edx, 23h ; '#'
0x180003440  mov     r9d, edi
0x180003443  call    WPP_SF_d
0x180003448  mov     eax, edi
0x18000344a  add     rsp, 30h
0x18000344e  pop     r15
0x180003450  pop     r14
0x180003452  pop     rdi
0x180003453  pop     rsi
0x180003454  pop     rbx
0x180003455  retn
```
