# CNetDiagHelperImpl::Initialize(ulong,tagHELPER_ATTRIBUTE * const)

- ea: `0x1800081b0`
- end: `0x1800082e7`
- name: `?Initialize@CNetDiagHelperImpl@@UEAAJKQEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `311`
- prototype: `int(CNetDiagHelperImpl *__hidden this, unsigned int, struct tagHELPER_ATTRIBUTE *const)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180004ac4`
- `0x1800081b0`
- `0x180011ef0`
- `0x180012ca0`
- `0x180012d86`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000829f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000829f`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::Initialize(
        CNetDiagHelperImpl *this,
        unsigned int a2,
        struct tagHELPER_ATTRIBUTE *const a3)
{
  __int64 result; // rax
  int v7; // ebp
  const struct tagHelperAttributeInfo near *const *v8; // rdi
  int v9; // r12d
  __int64 v10; // r15
  __int64 i; // r14
  __int64 v12; // rax
  bool v13; // zf
  __int64 j; // rdi

  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 1, 0) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a2 && !*((_DWORD *)this + 6) && !*((_QWORD *)this + 4) )
    return 0;
  result = _attributes_array_t::Copy((LPVOID *)this + 3, a2, a3);
  if ( (int)result >= 0 )
  {
    v7 = 0;
    v8 = &CNetDiagHelperImpl::m_attrInfos;
    if ( !a2 )
      return 0;
LABEL_8:
    if ( v8 && (v9 = *((_DWORD *)v8 + 2)) != 0 )
    {
      v10 = *((_QWORD *)this + 4);
      if ( v10 )
      {
        for ( i = 0; (unsigned int)i < *((_DWORD *)this + 6); i = (unsigned int)(i + 1) )
        {
          if ( *(_DWORD *)(v10 + 144 * i + 8) == v9 )
          {
            v12 = *(_QWORD *)(v10 + 144 * i);
            if ( *v8 )
            {
              if ( !v12 )
                continue;
              v13 = wcsncmp_0(*(const wchar_t **)(v10 + 144 * i), *(const wchar_t **)v8, 0xFFu) == 0;
            }
            else
            {
              v13 = v12 == 0;
            }
            if ( v13 )
            {
              if ( ++v7 < a2 )
              {
                v8 += 2;
                goto LABEL_8;
              }
              return 0;
            }
          }
        }
        for ( j = 0; (unsigned int)j < *((_DWORD *)this + 6); j = (unsigned int)(j + 1) )
          _attribute_t::FreeAll((LPVOID *)(*((_QWORD *)this + 4) + 144 * j));
      }
      CoTaskMemFree(*((LPVOID *)this + 4));
      *((_QWORD *)this + 4) = 0;
      *((_DWORD *)this + 6) = 0;
      MicrosoftTelemetryAssertTriggeredNoArgs();
      return 2147942487LL;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800081b0  push    rbx
0x1800081b2  push    rbp
0x1800081b3  push    rsi
0x1800081b4  push    rdi
0x1800081b5  push    r12
0x1800081b7  push    r14
0x1800081b9  push    r15
0x1800081bb  sub     rsp, 20h
0x1800081bf  mov     rbx, rcx
0x1800081c2  mov     rdi, r8
0x1800081c5  mov     ecx, 1
0x1800081ca  mov     esi, edx
0x1800081cc  xor     eax, eax
0x1800081ce  lock cmpxchg [rbx+10h], ecx
0x1800081d3  jz      short loc_1800081DA
0x1800081d5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800081da  test    esi, esi
0x1800081dc  jnz     short loc_1800081EE
0x1800081de  cmp     [rbx+18h], esi
0x1800081e1  jnz     short loc_1800081EE
0x1800081e3  cmp     qword ptr [rbx+20h], 0
0x1800081e8  jz      loc_1800082D5
0x1800081ee  mov     r8, rdi; struct tagHELPER_ATTRIBUTE *
0x1800081f1  lea     rcx, [rbx+18h]; this
0x1800081f5  mov     edx, esi; unsigned int
0x1800081f7  call    ?Copy@_attributes_array_t@@QEAAJKPEAUtagHELPER_ATTRIBUTE@@@Z; _attributes_array_t::Copy(ulong,tagHELPER_ATTRIBUTE *)
0x1800081fc  test    eax, eax
0x1800081fe  js      loc_1800082D7
0x180008204  xor     ebp, ebp
0x180008206  lea     rdi, ?m_attrInfos@CNetDiagHelperImpl@@0QBUtagHelperAttributeInfo@@B; tagHelperAttributeInfo const near * const CNetDiagHelperImpl::m_attrInfos
0x18000820d  test    esi, esi
0x18000820f  jz      loc_1800082D5
0x180008215  test    rdi, rdi
0x180008218  jz      loc_1800082D5
0x18000821e  mov     r12d, [rdi+8]
0x180008222  test    r12d, r12d
0x180008225  jz      loc_1800082D5
0x18000822b  mov     r15, [rbx+20h]
0x18000822f  test    r15, r15
0x180008232  jz      short loc_18000829B
0x180008234  xor     r14d, r14d
0x180008237  cmp     [rbx+18h], r14d
0x18000823b  jbe     short loc_18000827C
0x18000823d  lea     rcx, [r14+r14*8]
0x180008241  add     rcx, rcx
0x180008244  cmp     [r15+rcx*8+8], r12d
0x180008249  jnz     short loc_180008273
0x18000824b  mov     rdx, [rdi]; String2
0x18000824e  mov     rax, [r15+rcx*8]
0x180008252  test    rdx, rdx
0x180008255  jz      short loc_18000826E
0x180008257  test    rax, rax
0x18000825a  jz      short loc_180008273
0x18000825c  mov     r8d, 0FFh; MaxCount
0x180008262  mov     rcx, rax; String1
0x180008265  call    wcsncmp_0
0x18000826a  test    eax, eax
0x18000826c  jmp     short loc_180008271
0x18000826e  test    rax, rax
0x180008271  jz      short loc_1800082C6
0x180008273  inc     r14d
0x180008276  cmp     r14d, [rbx+18h]
0x18000827a  jb      short loc_18000823D
0x18000827c  xor     edi, edi
0x18000827e  cmp     [rbx+18h], edi
0x180008281  jbe     short loc_18000829B
0x180008283  lea     rcx, [rdi+rdi*8]
0x180008287  shl     rcx, 4
0x18000828b  add     rcx, [rbx+20h]; this
0x18000828f  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x180008294  inc     edi
0x180008296  cmp     edi, [rbx+18h]
0x180008299  jb      short loc_180008283
0x18000829b  mov     rcx, [rbx+20h]; pv
0x18000829f  call    cs:__imp_CoTaskMemFree
0x1800082a6  nop     dword ptr [rax+rax+00h]
0x1800082ab  mov     qword ptr [rbx+20h], 0
0x1800082b3  mov     dword ptr [rbx+18h], 0
0x1800082ba  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800082bf  mov     eax, 80070057h
0x1800082c4  jmp     short loc_1800082D7
0x1800082c6  inc     ebp
0x1800082c8  cmp     ebp, esi
0x1800082ca  jnb     short loc_1800082D5
0x1800082cc  add     rdi, 10h
0x1800082d0  jmp     loc_180008215
0x1800082d5  xor     eax, eax
0x1800082d7  add     rsp, 20h
0x1800082db  pop     r15
0x1800082dd  pop     r14
0x1800082df  pop     r12
0x1800082e1  pop     rdi
0x1800082e2  pop     rsi
0x1800082e3  pop     rbp
0x1800082e4  pop     rbx
0x1800082e5  retn
```
